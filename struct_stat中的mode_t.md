# struct stat中的mode_t
*****
```c
S_IFMT      0170000     文件类型的位遮罩  
S_IFSOCK    0140000     socket  
S_IFLNK     0120000     符号链接(symbolic link)  
S_IFREG     0100000     一般文件  
S_IFBLK     0060000     区块装置(block device)  
S_IFDIR     0040000     目录  
S_IFCHR     0020000     字符装置(character device)  
S_IFIFO     0010000     先进先出(fifo)  
S_ISUID     0004000     文件的(set user-id on execution)位  
S_ISGID     0002000     文件的(set group-id on execution)位  
S_ISVTX     0001000     文件的sticky位  
S_IRWXU     00700       文件所有者的遮罩值(即所有权限值)  
S_IRUSR     00400       文件所有者具可读取权限  
S_IWUSR     00200       文件所有者具可写入权限  
S_IXUSR     00100       文件所有者具可执行权限  
S_IRWXG     00070       用户组的遮罩值(即所有权限值)  
S_IRGRP     00040       用户组具可读取权限  
S_IWGRP     00020       用户组具可写入权限  
S_IXGRP     00010       用户组具可执行权限  
S_IRWXO     00007       其他用户的遮罩值(即所有权限值)  
S_IROTH     00004       其他用户具可读取权限  
S_IWOTH     00002       其他用户具可写入权限  
S_IXOTH     00001       其他用户具可执行权限  
摘自《Linux C 函数库参考手册》
```

