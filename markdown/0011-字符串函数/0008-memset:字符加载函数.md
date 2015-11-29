函数原型：void *memset(void *s, int c, unsigned n)
头文件：#include<string.h>
是否是标准函数：是
函数功能：把c复制到s所指向的对象的前n个字符的每一个字符中。
返回值：s的值
例程如下：应用memset函数替换字符串中的字符。
[code=java]
#include <string.h> 
#include <stdio.h> 
#[Keywords]int #main(void) 
{ 
   #[Keywords]char #*str=#[Fields]"AAAAAAAAAAAAAAAAAA"#;
   #printf(#[Fields]"The original string is:    %s\n"#,str);
   #memset(str,#[Fields]'B'#,9);
   #printf(#[Fields]"The string after memset is:%s\n"#,str);
#}
[/code]
[color=blue]例程说明：
（1）首先初始化字符串“AAAAAAAAAAAAAAAAAA”， 将首地址赋值给str。
（2）显示该字符串。
（3）利用函数memset将字符串str的前9个字符替换为’B’。
（4）显示替换后的字符串。
本例程的运行结果为：
[code=java]
The original string is:    AAAAAAAAAAAAAAAAAA
The string after memset is:BBBBBBBBBAAAAAAAAA
[/code]