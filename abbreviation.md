# 英语单词缩写
********
**rc** run configure
**texmf** text metafont
**TDS**  TeX Directory Structure  latex
**usr** Unix System Resource
**asm** Architecture Specific Macros  /usr/include/asm
0、项目名：
Linux -- LINUs' uniX (开个玩笑不是这样的，别当真）
GNU -- Gnu is Not Unix
1、目录名：
/boot：顾名思义
/root ：同上
/run：同上
/home：同上
/etc：ETCetera
/bin：BINaries
/dev：DEVices
/lib：LIBraries
/mnt：MouNT
/proc：PROCesses
/tmp：TeMPorary
/var：VARiable
/srv：SeRVices
/opt：OPTional
/sbin：Super BINaries
or Superuser BINaries
/sys：SYStem
/usr：Unix System Resources
or Unix Software Resources
or Unix Shared Resources（这个很重要，很多人会认为这个是user）
2、常用命令：
2.1、文件及文件夹管理：
ls -- LiSt
cd -- Change Directory
pwd -- Print Working Directory
cp -- CoPy
mv -- MoVe
rm -- ReMove
pushd -- PUSH to Directory
popd -- POP from Directory
mkdir -- MaKe DIRectory
rmdir -- ReMove DIRectory
cat -- CATenate
or conCATenate
sed -- Stream EDitor
diff -- DIFFerence
wc -- Word Count
chmod -- CHange MODe
chown -- CHange OWNer
chgrp -- CHange GRouP
awk -- Aho Weinberger and Kernighan
gawk -- Gnu AWK
mawk -- Minimal AWK
grep -- General Regular Expression Print
ln -- LiNk
tar -- TARball
2.2、硬件管理：
df -- Disk Free
du -- Disk Usage
dd -- Data Description（有说是Convert and Copy， 但是cc被用掉了，就用dd了）
parted -- PARTition EDitor
fdisk -- Format DISK
lspci -- LiSt Peripheral Component Interconnect
lscpu -- LiSt Central Process Unit
lsusb -- LiSt Universal Serial Bus
lsblk -- LiSt BLocK
mdadm -- Multiple Disk And Device Manager
2.2.1、lvm
lvm -- Logical Volume Manager
pvcreate -- Physical Volume CREATE
vgcreate -- Volume Group CREATE
lvcreate -- Logical Volume CREATE
pvdisplay -- Physical Volume DISPLAY
vgdisplay -- Volume Group DISPLAY
lvdisplay -- Logical Volume DISPLAY
pvresize -- Physical Volume RESIZE
vgresize -- Volume Group RESIZE
lvresize -- Logical Volume RESIZE
pvextend -- Physical Volume EXTEND
vgextend -- Volume Group EXTEND
lvextend -- Logical Volume EXTEND
pvremove -- Physical Volume REMOVE
vgremove -- Volume Group REMOVE
lvremove -- Logical Volume REMOVE
pvs -- Physical Volume Status
vgs -- Volume Group Status
lvs -- Logical Volume Status
2.3、软件及软件包管理：
man -- MANual
apt -- Advanced Packaging Tool
dpkg -- Debian PacKaGe
yum -- Yellow dog Updater, Modified
rpm -- RPM Package Manager
or Redhat Package Manager
2.4、用户及用户组管理：
useradd -- USER Add
userdel -- USER DELete
usermod -- USER MODify
users -- USER Status
groupadd -- GROUP ADD
groupdel -- GROUP DELete
groupmod -- GROUP MODify
groupmems -- GROUP MEMberS
2.5、系统管理：
depmod -- DEPend MODule
lsmod -- LiSt MODule
modprobe -- MODule PROBE
modinfo -- MODule INFOrmation
insmod -- INSert MODule
rmmod -- ReMove MODule
mkfs -- MaKe FileSystem
fsck -- File System Consistency Check
ps -- Processes Status
su -- Substitute User
bash -- Bourne Again SHell
dash -- Debian Almquist SHell
init -- INITialization
ssh -- Secure SHell
wine -- Wine Is Not an Emulator
exec -- EXECute
fstab -- FileSystem TABle
passwd -- PASSWorD
chpasswd -- CHange PASSWorD
pwconv -- PassWord CONVert
pwunconv -- PassWord UNCONVert
tty -- TeleTYpe
sudo -- SuperUser DO
grub -- GRand Unified Bootloader
tzselect -- Time Zone SELECT
sync -- SYNChronize
systemd -- SYSTEM Daemon (里面有systemctl bootctl journalctl loginctl localectl timedatectl 等等，都是blablabla ConTroL）
2.6、编辑器：
ed -- EDitor
nano -- Nano's ANOther editor
emacs -- Editor MACroS（还有很多全称，就不罗列了，这个接受度比较广）
vi -- VIsual
vim -- Vi Improved
2.7、编译器：
cc -- C Compiler
gcc -- Gnu Compiler Collection（作为一个软件集被你下载下来编译安装的时候）
gcc -- Gnu C Compiler (作为一个软件被你调用来编译C程序的时候）
g++ -- Gnu c++ compiler
gcj -- Gnu Compiler for Java
yacc -- Yet Another Compiler Compiler
guile -- Gnu Ubiquitous Intelligent Language for Extensions
gas -- Gnu Assembler
php -- PHP：Hypertext Preprocessor
ld -- LoaD
gdb -- Gnu DeBug
tcl -- Tool Command Line
3、图形界面：
gnome -- GNu Object Model Environment
gdm -- Gnome Display Manager
gtk -- Graphic user interface ToolKit
qt -- ………………Toolkit（不说Q了，用Q只是因为在开发者的Emacs中Q特别漂亮…………）
kde -- K Desktop Environment
lxde -- Lightweight X11 Desktop Environment
xfce -- XForms Common Environment
4、参数（声明：只是通常会使用的参数，并不一定是通用参数，使用时请注意）：
-h | --help：help
-v | --version：version（吐槽一下java）
5、许可证：
gnu gpl : Gnu General Public License
gnu lgpl : Gnu General Lesser Public License
gfdl : Gnu Free Documentation License
agpl : Affero General Public License（或简写为Affero gpl)
apsl : Apple Public Source License
bsd : Berkeley Software Distribution License
