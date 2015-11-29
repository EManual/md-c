函数原型： int isxdigit(int c);
头文件：#include<ctype.h>
是否是标准函数：是
函数功能：检查字符c是否为十六进制数字。
返回值：当c为A-F,a-f或0-9之间的十六进制数字时，返回非零值，否则返回0。
例程如下：应用isxdigit函数检查字符属性。
[code=java]
#include <stdio.h>
#include <ctype.h>
#[Keywords]int #main(void)
{
     #[Keywords]char #c;
     #c=#[Fields]'f'#;
     #printf(#[Fields]"%c:%s\n"#,c,isxdigit(c)?#[Fields]"yes"#:#[Fields]"no"#);
     #c=#[Fields]'1'#;
     #printf(#[Fields]"%c:%s\n"#,c,isxdigit(c)?#[Fields]"yes"#:#[Fields]"no"#);
     #c=#[Fields]'$'#;
     #printf(#[Fields]"%c:%s\n"#,c,isxdigit(c)?#[Fields]"yes"#:#[Fields]"no"#);
     #getchar();
     #[Keywords]return #0;
#}
[/code]
[color=blue]例程说明：
本例程应用isxdigit函数判断字符'f'、'1'、'$'是否是十六进制数字，如果是，显示"yes",不是则显示"no"。本例程的运行结果是：
[code=java]
f:yes
1:yes
$:no
[/code]