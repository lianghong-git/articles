# POSIX标准和XSI扩展  
POSIX 表示可移植操作系统接口（Portable Operating System Interface ）。  电气和电子工程师协会（Institute of Electrical and Electronics Engineers，IEEE）  最初开发 POSIX 标准，是为了提高 UNIX 环境下应用程序的可移植性。然而，  POSIX 并不局限于 UNIX。许多其它的操作系统，例如 DEC OpenVMS 和   Microsoft Windows NT，都支持 POSIX 标准，尤其是 IEEE Std. 1003.1-1990  （1995 年修订）或 POSIX.1，POSIX.1 提供了源代码级别的 C 语言应用编程接口（API）给操作系统的服务程序，例如读写文件。POSIX.1 已经被国际标准化组织（International Standards Organization，ISO）所接受，被命名为   ISO/IEC 9945-1:1990 标准。  

### POSIX标准定义的必须的头文件(26项)  
<dirent.h>      ----------------------   目录项  
<fcntl.h>         ----------------------   文件控制  
<fnmatch.h>   ----------------------   文件名匹配类型  
<glob.h>         ----------------------   路径名模式匹配类型  
<grp.h>          ----------------------   组文件  
<netdb.h>      ----------------------   网络数据库操作  
<pwd.h>         ----------------------   口令文件  
<regex.h>      ----------------------   正则表达式  
<tar.h>           ----------------------   tar归档值  
<termios.h>    ----------------------   终端I/O  
<unistd.h>      ----------------------   符号常量  
<utime.h>       ----------------------   文件时间  
<wordexp.h>   ----------------------   字扩展类型  
<arpa/inet.h>  ----------------------   Internet定义  
<net/if.h>       ----------------------   套接字本地接口  
<netinet/in.h> ----------------------   Internet地址族  
<netinet/tcp.h>----------------------   传输控制协议定义  
<sys/mman.h>----------------------   内存管理声明  
<sys/select.h>----------------------   select函数  
<sys/socket.h>----------------------   套接字接口  
<sys/stat.h>    ----------------------   文件状态  
<sys/times.h>  ----------------------   进程时间  
<sys/types.h>  ----------------------   基本系统数据类型  
<sys/un.h>      ----------------------   UNIX域套接字定义  
<sys/utsname.h>----------------------系统名  
<sys/wait.h>    ----------------------   进程控制  

### POSIX标准定义的XSI扩展头文件(26项)  
<cpio.h>          ----------------------   cpio归档值  
<dlfcn.h>         ----------------------   动态链接  
<fmtmsg.h>     ----------------------   消息显示结构  
<ftw.h>            ----------------------   文件树漫游  
<iconv.h>        ----------------------   代码集转换实用程序  
<langinfo.h>    ----------------------   语言信息常量  
<libgen.h>       ----------------------   模式匹配函数定义  
<monetary.h>  ----------------------   货币类型  
<ndbm.h>        ----------------------   数据库操作  
<nl_types.h>   ----------------------   消息类别  
<poll.h>           ----------------------   轮询函数  
<search.h>      ----------------------   搜索表  
<strings.h>      ----------------------   字符串操作  
<syslog.h>      ----------------------   系统出错日志记录  
<ucontext.h>   ----------------------   用户上下文  
<ulimit.h>        ----------------------   用户限制  
<utmpx.h>       ----------------------   用户帐户数据库  
<sys/ipc.h>      ----------------------   IPC  
<sys/msg.h>    ----------------------   消息队列  
<sys/resource.h>-------------------   资源操作  
<sys/sem.h>    ----------------------   信号量  
<sys/shm.h>    ----------------------   共享存储  
<sys/statvfs.h>----------------------   文件系统信息  
<sys/time.h>    ----------------------   时间类型  
<sys/timeb.h>  ----------------------   附加的日期和时间定义  
<sys/uio.h>      ----------------------   矢量I/O操作  

### POSIX标准定义的可选头文件(8项)    
<aio.h>            ----------------------   异步I/O  
<mqueue.h>    ----------------------   消息队列  
<pthread.h>    ----------------------   线程  
<sched.h>       ----------------------   执行调度  
<semaphore.h>---------------------   信号量  
<spawn.h>       ----------------------   实时spawn接口  
<stropts.h>      ----------------------   XSI STREAMS接口  
<trace.h>         ----------------------   时间跟踪    

Single UNIX Specification是POSIX.1标准的超集，定义了一些附加的接口，这些接口扩展了基本的POSIX.1规范的功能。相应的系统接口全集被称为X/Open系统接口（XSI，X/Open System Interface） ，XSI还定义了实现必须支持的POSIX.1的哪些可选部分才能认为是遵循XSI的。它们包括文件同步，存储映射文件，存储保护及线程接口。只有遵循XSI的实现才能称为UNIX操作系统。
#### linux常用头文件如下： 
##### POSIX标准定义的头文件  
<dirent.h>        目录项  
<fcntl.h>         文件控制  
<fnmatch.h>    文件名匹配类型  
<glob.h>    路径名模式匹配类型  
<grp.h>        组文件  
<netdb.h>    网络数据库操作  
<pwd.h>        口令文件  
<regex.h>    正则表达式  
<tar.h>        TAR归档值  
<termios.h>    终端I/O  
<unistd.h>    符号常量  
<utime.h>    文件时间  
<wordexp.h>    字符扩展类型  

<arpa/inet.h>    INTERNET定义  
<net/if.h>    套接字本地接口  
<netinet/in.h>    INTERNET地址族  
<netinet/tcp.h>    传输控制协议定义  

<sys/mman.h>    内存管理声明  
<sys/select.h>    Select函数  
<sys/socket.h>    套接字借口  
<sys/stat.h>    文件状态  
<sys/times.h>    进程时间  
<sys/types.h>    基本系统数据类型  
<sys/un.h>    UNIX域套接字定义  
<sys/utsname.h>    系统名  
<sys/wait.h>    进程控制  
##### POSIX定义的XSI扩展头文件  
<cpio.h>    cpio归档值  
<dlfcn.h>    动态链接  
<fmtmsg.h>    消息显示结构  
<ftw.h>        文件树漫游  
<iconv.h>    代码集转换使用程序  
<langinfo.h>    语言信息常量  
<libgen.h>    模式匹配函数定义  
<monetary.h>    货币类型  
<ndbm.h>    数据库操作  
<nl_types.h>    消息类别  
<poll.h>    轮询函数  
<search.h>    搜索表  
<strings.h>    字符串操作  
<syslog.h>    系统出错日志记录  
<ucontext.h>    用户上下文  
<ulimit.h>    用户限制  
<utmpx.h>    用户帐户数据库  

<sys/ipc.h>    IPC(命名管道)  
<sys/msg.h>    消息队列  
<sys/resource.h>资源操作  
<sys/sem.h>    信号量  
<sys/shm.h>    共享存储  
<sys/statvfs.h>    文件系统信息  
<sys/time.h>    时间类型  
<sys/timeb.h>    附加的日期和时间定义  
<sys/uio.h>    矢量I/O操作  
##### POSIX定义的可选头文件  
<aio.h>        异步I/O  
<mqueue.h>    消息队列  
<pthread.h>    线程  
<sched.h>    执行调度  
<semaphore.h>    信号量  
<spawn.h>     实时spawn接口  
<stropts.h>    XSI STREAMS接口  
<trace.h>     事件跟踪  
