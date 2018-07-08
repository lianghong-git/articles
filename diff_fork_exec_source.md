# 在shell脚本中调用另一个脚本的三种不同方法(fork, exec, source)  

1. fork  ( /directory/script.sh)   
	如果shell中包含执行命令，那么子命令并不影响父级的命令，在子命令执行完后再执行父级命令。子级的环境变量不会影响到父级。fork是最普通的, 就是直接在脚本里面用/directory/script.sh来调用script.sh这个脚本.运行的时候开一个sub-shell执行调用的脚本，sub-shell执行的时候, parent-shell还在。sub-shell执行完毕后返回parent-shell. sub-shell从parent-shell继承环境变量.但是sub-shell中的环境变量不会带回parent-shell.

2. exec (exec /directory/script.sh)  
	执行子级的命令后，不再执行父级命令。exec与fork不同，不需要新开一个sub-shell来执行被调用的脚本.  被调用的脚本与父脚本在同一个shell内执行。但是使用exec调用一个新脚本以后, 父脚本中exec行之后的内容就不会再执行了。这是exec和source的区别

3. source (source /directory/script.sh)  
	执行子级命令后继续执行父级命令，同时子级设置的环境变量会影响到父级的环境变量。与fork的区别是不新开一个sub-shell来执行被调用的脚本，而是在同一个shell中执行. 所以被调用的脚本中声明的变量和环境变量, 都可以在主脚本中得到和使用.
