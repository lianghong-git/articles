# chroot用法和安装脚本  
  
chroot是操作系统级的“虚拟机”，其功能是切换程序运行时的根目录，将程序限制在指定的根目录中，从而隔离应用程序。在chroot中运行的程序实际上使用的是真实系统的内核和资源，所以性能不会有损耗。  
其好处主要有：  
  
* 增强主机安全性  
在chroot中的程序不会访问到真实的系统文件，如真实系统的passwd等文件，和Windows下的沙箱类似，尤其适合对高风险的应用，如web等  
  
* 独立的程序运行环境  
运行在chroot中的程序使用的是chroot中的资源，不会使用主机提供的库文件等。要想在程序能在chroot中运行，就要解决依赖关系，所以用chroot还可以把程序“绿色化”，配置好的chroot环境，打包好丢到其它服务器直接就可以运行。这一特性也方便了运维和开发。  
  
* 限制资源访问  
可以限制chroot环境中用户能使用的命令，例如：如果不想用户使用passwd命令，不要把passwd命令放到chroot环境中就行了。出与安全考虑运行在chroot中的程序建议给最小权限。  
  
所需条件：  
  
1. 相同的内核，linux和*BSD是不同的  
2. chroot需要root权限  
3. 一个可运行的shell  

建立一个最小的chroot环境：  
chroot目录是/opt/chroot,在其下面建立一个bin目录，存放shell，这里用默认的bash  
`mkdir  -p /opt/chroot/bin`    
拷贝bash二进制文件：  
`cp /bin/bash /opt/chroot/bin`   
  
解决bash的依赖关系：  
`ldd /bin/bash`  
>linux-vdso.so.1 => (0x00007fffd95ff000)  
libtinfo.so.5 => /lib64/libtinfo.so.5 (0x00007f82a7b54000)  
libdl.so.2 => /lib64/libdl.so.2 (0x00007f82a7950000)  
libc.so.6 => /lib64/libc.so.6 (0x00007f82a75bb000)  
/lib64/ld-linux-x86-64.so.2 (0x00007f82a7d7e000)  

整理一下格式：  
  
>ldd /opt/chroot/bin/bash|grep -o "/\(\usr\|lib\).[^ \ ]*"  
/lib64/libtinfo.so.5  
/lib64/libdl.so.2  
/lib64/libc.so.6  
/lib64/ld-linux-x86-64.so.2  

所有依赖的库文件都在/lib64下，在/opt/chroot目录下建立lib64目录，并将依赖的库拷贝进去：  
  
`cp $(ldd /opt/chroot/bin/bash | grep lib64 | sed -sre 's/(.+)(\/lib64\/\S+).+/\2/g') /opt/chroot/lib64/`  
运行chroot：  
`chroot /opt/chroot`   
格式：  
`chroot chroot目录 shell`  
 这样就进入了chroot环境，这时只能使用pwd、cd这类bash内置的命令，没有ls、mkdir这类系统的命令，想运行哪个命令用相同的方式加入chroot环境。退出chroot环境直接exit即可。  
  
 对于简单的系统命令或软件可以这样配置，如果是nginx、python这类依赖非常复杂的软件，不建议这样做。我的做法是在centos下安装一个centos的base系统到chroot目录，大概有300多兆，在配置好环境后并精简掉没用的软件。精简要比解决依赖关系容易多了，做好这个后可以打包拿到其它linux内核的系统上使用。  
  
 直接上脚本：  
```bash   
 #!/bin/sh  
 #  
 # Build a chroot with a CentOS 6.6 base install.  
 #  
  
 CHROOT=/tmp/chroot  
  
 mkdir -p $CHROOT/var/lib/rpm  
 rpm --rebuilddb --root=$CHROOT  
  
 wget http://mirror.centos.org/centos/6.6/os/x86_64/Packages/centos-release-6-6.el6.centos.12.2.x86_64.rpm  
 rpm -i --root=$CHROOT --nodeps centos-release-6-6.*.rpm  
  
 yum --installroot=$CHROOT install -y rpm-build yum  
  
 mkdir -p $CHROOT/proc  
 mount --bind /proc $CHROOT/proc  
  
 mkdir -p $CHROOT/dev  
 mount --bind /dev $CHROOT/dev  
  
 mkdir -p $CHROOT/etc  
 cp /etc/resolv.conf $CHROOT/etc/resolv.conf  
  
 mkdir -p $CHROOT/root  
 cp $CHROOT/etc/skel/.??* $CHROOT/root  
  
 rm -rf centos-release-6-6.*.rpm  
```  
  
参考文章：  
  
http://www.cyberciti.biz/faq/howto-run-nginx-in-a-chroot-jail/  
https://wiki.archlinux.org/index.php/Nginx  
