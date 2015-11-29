函数原型：char *strlwr(char *str,);
头文件：#include<string.h>
是否是标准函数：否
函数功能：将字符串原有大写字符全部转换为小写字符，也就是将字符串str中的所有字符变成小写。
返回值：返回指向被转换字符串的指针
例程如下： 应用strlwr将字符串转换成小写字符。
[code=java]
#include <stdio.h> 
#include <string.h>
#[Keywords]int #main(void) 
{ 
    #[Keywords]char #*s=#[Fields]"You#[Fields]'ll Never Walk Alone"#;
    #printf(#[Fields]"%s"#,strlwr(s));
    #getch();
    #[Keywords]return #0;
#}
[/code]
[color=blue]例程说明：
（1）首先，程序声明了一个字符串为待转换字符串并赋予初值。
（2）程序通过调用strlwr将字符串中的所有大写字符转换成小写字符，并返回转换后的结果。
（3）最后将转换结果打印出来。
本例程的运行结果是：
[code=java]
you'll never walk alone 
[/code]