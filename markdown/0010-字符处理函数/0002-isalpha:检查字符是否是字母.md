函数原型：int isalpha( int c );
头文件：#include<ctype.h>
是否是标准函数：是
函数功能：检查字符c 是否是字母（alpha）。
返回值：是字母返回1，否则返回0。
例程如下：应用isalpha检查字符属性。
[code=java]
#include <stdio.h>
#include <ctype.h> 
#[Keywords]int #main( #[Keywords]void #) 
{ 
   #[Keywords]char #c,ch;
   #scanf(#[Fields]"%c"#,&c);
   #ch=getchar();
  #[Keywords] while#(c!=#[Fields]'e'#) {
        #[Keywords]if#(isalpha (c))
            #printf(#[Fields]"This is a alpha \n"#);
       #[Keywords] else#
            #printf(#[Fields]"This is not a alpha\n"#);
        #scanf(#[Fields]"%c"#,&c);
        #ch=getchar();
   #}
   #[Keywords]return #1;
#}
[/code]
[color=blue]例程说明：
本例程但只判断输入的字符是否是字母，如果是字母，则在屏幕上显示"This is a alpha "提示信息，否则显示"This is not a alpha"提示信息。
本例程的运行结果为：
[code=java]
a
This is a alpha
3
This is not a alpha
$
This is not a alpha
e
[/code]