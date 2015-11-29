函数原型：int fputs(char *string, FILE *fp);
头文件：#include<stdio.h>
是否是标准函数：是
函数功能：将string所指的字符串输出到fp指向的文件中。该函数与fgets相对，第一个参数为字符串指针。与fgets函数不同的是，fputs函数没有字符串长度的限制，只是将string指向的字符串输出到文件中。
返回值：成功返回0，否则返回非0。
例程如下 应用fputs函数向文件中输出字符串。
[code=java]
#include <stdio.h> 
#[Keywords]int #main(void) 
{ 
   #FILE *fp;
   #[Keywords]char #str[]=#[Fields]"This is a test!"#;
   #/*以写的方式打开名为test.txt的文件*/
   #fp=fopen(#[Fields]"test.txt"#,#[Fields]"w"#);
   #/*将字符串写入文件*/
   #fputs(str,fp);
   #fclose(fp);
   #[Keywords]return #0;
#}
[/code]
[color=blue]例程说明：
（1）首先用字符数组str存储一个字符串，并以写的方式打开名为test.txt的文件。
（2）再用fputs函数将该字符串输出到test.txt的文件中。