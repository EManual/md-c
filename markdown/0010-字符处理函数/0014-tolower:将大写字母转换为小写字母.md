函数原型：int tolower(int c);
头文件：#include<ctype.h>
是否是标准函数：是
函数功能：将c转化为相应的小写字母。
返回值：如果c为大写英文字母，则返回对应的小写字母；否则返回原来的值。
例程如下： 应用tolower函数将大写字母转换为小写字母。
[code=java]
#include <stdio.h>
#include <ctype.h>
#[Keywords]int #main(void)
{
    #[Keywords]char #str[]=#[Fields]"This Is A Test!"#;
    #[Keywords]int #i;
    #printf(#[Fields]"%s\n"#,str);
    #[Keywords]for#(i=0;i<strlen(str);i++)
    #{
        #putchar(tolower(str[i]));
    #}
    #getchar();
    #[Keywords]return #0;
#}
[/code]
[color=blue]例程说明：
（1）首先，将字符串"This Is A Test!"存入以str为首地址的缓冲区中，并将该字符串显示在终端屏幕上。
（2）应用"This Is A Test!"函数将该字符串中大写字母转换为小写字母，并输出。本
注意：本例程将字符串中大写字母转换为小写字母并输出，但并不改变原数组中的内容，只是在输出时将大写字母转换为小写字母，而本身是小写字母的字符或非字母字符，则返回原值。本例程的运行结果是：
[code=java]
This Is A Test!
this is a test!
[/code]