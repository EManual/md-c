函数原型：int isgraph(int c);
头文件：#include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否是除了空格符外的可打印字符，其ASCII码在0x21-0x7e之间。
返回值：是除了空格符外的可打印字符返回1，否则返回0。
例程如下： 应用isgraph函数判断可打印字符。
[code=java]
#include <stdio.h>
#include <ctype.h>
#[Keywords]int #main(void)
{
    #[Keywords]int #c;
    #c=#[Fields]'A'#;
    #printf(#[Fields]"%c:%s\n"#,c,isgraph(c)?#[Fields]"yes"#:#[Fields]"no"#);
    #c=#[Fields]' '#;
    #printf(#[Fields]"%c:%s\n"#,c,isgraph(c)?#[Fields]"yes"#:#[Fields]"no"#);
    #c=0x7f;
    #printf(#[Fields]"%c:%s\n"#,c,isgraph(c)?#[Fields]"yes"#:#[Fields]"no"#);
    #getchar();
    #[Keywords]return #0;
#}
[/code]
[color=blue]例程说明：
本例程应用isgraph函数判断字符'A'、''、0x7f是否是除了空格符外的可打印字符。如果是，显示"yes",不是则显示"no"。本例程的运行结果是：
[code=java]
A:yes
 :no
?:no
[/code]