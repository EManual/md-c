函数原型：int iscntrl( int c );
头文件：#include<ctype.h>
是否是标准函数：是
函数功能：检查字符c 是否是控制字符，控制字符的ASCII码在0到0x1F之间。
返回值：是控制字符返回1，否则返回0。
例程如下：应用iscntrl检查字符属性。
[code=java]
#include <stdio.h>
#include <ctype.h> 
#[Keywords]int #main(void)
{
    #[Keywords]char #c,ch;
    #printf(#[Fields]"Input some character until contrl character\n"#);
    #scanf(#[Fields]"%c"#,&c);
    #ch=getchar();
   #[Keywords] while#(!iscntrl(c)){
        #scanf(#[Fields]"%c"#,&c);
        #ch=getchar();
    #};
    #[Keywords]return #0;
#}
[/code]
[color=blue]例程说明：
输入的字符不是控制字符时，可以一直输入下去，一旦输入了控制字符，程序结束。
注意：每输入一个字符时，要以回车结束。
本例程的运行结果为：
[code=java]
a
b
[/code]