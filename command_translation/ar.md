# ar-create,modify and extract from archive
nm-list symbol from obj files -可以查看动态库中都有些什么函数
当我们的程序中有经常使用的模块，而且这种模块在其他程序中也会用到，这时按照软件重用的思想，我们应该将它们生成库，使得以后编程可以减少开发代码量。这里介绍两个命令ar和nm，用来对库操作。

1、ar基本用法

ar命令可以用来创建、修改库，也可以从库中提出单个模块。库是一单独的文件，里面包含了按照特定的结构组织起来的其它的一些文件（称做此库文件的member）。原始文件的内容、模式、时间戳、属主、组等属性都保留在库文件中。

下面是ar命令的格式：

ar[-][abcfilNoPsSuvV][membername][count]archivefiles...

例如我们可以用ar rvl ibtest.a hello.o hello1.o来生成一个库，库名字是test，链接时可以用-ltest链接。该库中存放了两个模块hello.o和hello1.o。选项前可以有 ‘-’字符，也可以没有。下面我们来看看命令的操作选项和任选项。现在我们把部分称为操作选项，而[abcfilNoPsSuvV]部分称为任选项。

中的操作选项在命令中只能并且必须使用其中一个，它们的含义如下：

d：从库中删除模块。按模块原来的文件名指定要删除的模块。如果使用了任选项v则列出被删除的每个模块。

m：该操作是在一个库中移动成员。当库中如果有若干模块有相同的符号定义(如函数定义)，则成员的位置顺序很重要。如果没有指定任选项，任何指定的成员将移到库的最后。也可以使用’a’，’b’，或’I’任选项移动到指定的位置。

p：显示库中指定的成员到标准输出。如果指定任选项v，则在输出成员的内容前，将显示成员的名字。如果没有指定成员的名字，所有库中的文件将显示出来。

q：快速追加。增加新模块到库的结尾处。并不检查是否需要替换。’a’，’b’，或’I’任选项对此操作没有影响，模块总是追加的库的结尾处。如果使用了任选项v则列出每个模块。这时，库的符号表没有更新，可以用’ars’或ranlib来更新库的符号表索引。

r：在库中插入模块(替换)。当插入的模块名已经在库中存在，则替换同名的模块。如果若干模块中有一个模块在库中不存在，ar显示一个错误消息，并不替换其他同名模块。默认的情况下，新的成员增加在库的结尾处，可以使用其他任选项来改变增加的位置。

t：显示库的模块表清单。一般只显示模块名。

x：从库中提取一个成员。如果不指定要提取的模块，则提取库中所有的模块。

下面在看看可与操作选项结合使用的任选项：

a：在库的一个已经存在的成员后面增加一个新的文件。如果使用任选项a，则应该为命令行中membername参数指定一个已经存在的成员名。

b：在库的一个已经存在的成员前面增加一个新的文件。如果使用任选项b，则应该为命令行中membername参数指定一个已经存在的成员名。

c：创建一个库。不管库是否存在，都将创建。

f：在库中截短指定的名字。缺省情况下，文件名的长度是不受限制的，可以使用此参数将文件名截短，以保证与其它系统的兼容。

i：在库的一个已经存在的成员前面增加一个新的文件。如果使用任选项i，则应该为命令行中membername参数指定一个已经存在的成员名(类似任选项b)。

l：暂未使用

N：与count参数一起使用，在库中有多个相同的文件名时指定提取或输出的个数。

o：当提取成员时，保留成员的原始数据。如果不指定该任选项，则提取出的模块的时间将标为提取出的时间。

P：进行文件名匹配时使用全路径名。ar在创建库时不能使用全路径名（这样的库文件不符合POSIX标准），但是有些工具可以。

s：写入一个目标文件索引到库中，或者更新一个存在的目标文件索引。甚至对于没有任何变化的库也作该动作。对一个库做ars等同于对该库做ranlib。

S：不创建目标文件索引，这在创建较大的库时能加快时间。

u：一般说来，命令arr…插入所有列出的文件到库中，如果你只想插入列出文件中那些比库中同名文件新的文件，就可以使用该任选项。该任选项只用于r操作选项。

v：该选项用来显示执行操作选项的附加信息。

V：显示ar的版本。
