条件编译是指编译时对源程序的某种控制。在一定的条件下，源程序中的某些特殊语句参加编译，而在另一种条件下，同样的这些语句不参加编译，也即C语言的语句是否有效要根据是否满足条件编译语句中设置的条件来决定，这就称为条件编译。

#### 常用命令及其格式

1. ifdef命令
```  
ifdef 标识符
	程序段1
else
	程序段2
endif
```
其功能是：当“标识符”已经被定义过(通常是用define命令定义)，则对“程序段l”进行编译，否则编译“程序段2”。其中“else”部分根据具体要求可以省略，即也可以为如下形式：
```  
ifdef 标识符
endif
```
2. ifndef命令
```  
ifndef 标识符
	程序段1
else
	程序段2
endif
```
其功能是：若“标识符”未被定义，则编译“程序段”，否则编译“程序段2”。正好与第一种形式的作用相反。

3. if命令
```  
if 表达式
	程序段1
else
	程序段2
endif
```
该格式中“if表达式”语句与前两种格式不同，if是关键字，“表达式”是常量表达式。其功能是：当“表达式”的值非0时．“程序段1”参加编译，否则“程序段2”参加编译。当然，根据需要，也可以没有else语句，即简化为如下格式：
```  
if 表达式
	程序段
endif
```

#### 条件编译命令的应用

使用条件编译命令可以对源程序的内容进行选择性的编译，比如在调试程序的时候，通常希望输出一些调试用的情息，而在调试完毕后，就不再需要输出这些信息了。

在学习编译预处理命令前，有一个解决方法是在调试程序的时候增加一些输出语句，而在调试完毕，生成最终需要的可执行文件时，再将源程序改动，删去这些语句，这种作法比较麻烦，在删除的过程中容易误删程序本身需要的语句，或少删了本来作为调试用的的语句，影响最终得到的可执行文件的运行与输出效果。另外，如果这段程序再需要调试时，又得把那些凋试语句逐一加上去。掌握条件编译语句后，可以用这类命令来辅助程序调试。

例如，在程序开头定义一个符号常数DEBUG(值为l或0)，在程序任何需要设置调试信息之处，加入以下信息：
```  
if DEBUG
	调试代码
endif
```
这里定义DEBUG为1时，为调试状态，即输出跟踪信息。在调试时，程序中定义DEBUG的语句为：
```  
define DEBUG 1
```
而调试结束后，将这条语句改为：
```  
define DEBUG 0
```
那么凡是加入
```  
if DEBUG
	调试代码
endif
```
的地方，调试代码便不再起作用。
这样，只需修改define DEBUG这一条语句，便达到了自动删除或增加程序中众多调试语句的效果。