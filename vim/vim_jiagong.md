# vim在每行行首或行尾添加/删除内容 
#### 添加
在每行行首添加相同的内容:  
>`%s/^/要添加的内容`  

在每行行尾添加相同的内容：  
>`%s/$/要添加的内容`  
#### 利用正则表达式删除代码段每行的行号
>`:%s/^\s*[0-9]*\s*//gc`  

其中，^表示行首，$表示行尾，\s表示空格，[0-9]表示0~9的数字，\*表示0或多个，`%s/^\s*[0-9]*\s*//gc`的意思是将每行以0或多个空格开始中间包含0或多个数字并以0或多个空格结束的字符串替换为空。
