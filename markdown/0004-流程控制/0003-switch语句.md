上节介绍的if条件选择语句—般适用于两路选择，即在两个分支中选择其中一个分支执行，虽然可以用嵌套的if语句或不嵌套的多个if语句来实现多路选择，但这样使得程序冗长，可读性降低。C语言中的swithc多分支选择语句，可更方便地直接用于多分支选挥。
switch多分支选择语句的—般形式如下：
[code=java]
#[Keywords]switch#(表达式)
{ 	#[Keywords]case #常量表达式1: 语句1
	#[Keywords]case #常量表达式2: 语句2
	#[Keywords]case #常量表达式3: 语句3
	…
	#[Keywords]case #常量表达式k: 语句k
	#[Keywords]default#: 语句k+1
}
[/code]
switch语句的执行过程是，当switch后面（）中的表达式的值与某一个case后面的常量表达式的值相等时，就执行此case后面的语句。若所有case中的常量表达式的值都没有与该表达式的值匹配的，就执行default后面的语句。
需要说明的是：
1）switch后面（）中的表达式，可以是整型或字符型表达式，也可以是枚举型数据。作为多分支选择判断的条件必须是整型、字符型或枚举型表达式，即其值为整数。
2）每一个case后面跟的是一个常量表达式，不能是变量表达式。即switchh后面（）中的表达式只能与常量表达式的值进行匹配比较。
3）每一个case的常量表达式的值必须互不相同，否则就会出现矛盾的现象（对表达式的值，有多个匹配对象，就有两种或多种执行方案）
4）执行完一个case后面的语句后，流程控制转移到下—个case继续执行。“case常量表达式”只是起语句标号作用，并不是在该处进行判断。在执行switch语句时，根据switch后面表达式的值找到匹配的入口地址，就从此标号开始执行，不再进行判断。因此，应该在执行一个case分支后，要使流程跳出switch语句的执行，即终止switch的执行。可以用一个break语句来实现，即在每一个case后的语句之后加上break语句。
在case后面可以包含一个以上语句，但可以不必用花括号括起来作为复合语句，因为系统会自动执行本case后的所有语句。当然，加上花括号构成复合语句也可以。
例0.8：输入10以内的数字，输出对应的英文单词，即1输出one，2输出two，3输出three …。
[code=java]
#include #[Fields]"stdio.h"#
main()
{
	#[Keywords]int #a;
	#printf(#[Fields]"input integer number(<10): "#);
	#scanf(#[Fields]"%d"#,&a);
	#[Keywords]switch #(a){
		#[Keywords]case #1:printf(#[Fields]"one\n"#);#[Keywords]break#;
		#[Keywords]case #2:printf(#[Fields]"two\n"#);#[Keywords]break#;
		#[Keywords]case #3:printf(#[Fields]"three\n"#);#[Keywords]break#;
		#[Keywords]case #4:printf(#[Fields]"four\n"#);#[Keywords]break#;
		#[Keywords]case #5:printf(#[Fields]"five\n"#);#[Keywords]break#;
		#[Keywords]case #6:printf(#[Fields]"six\n"#);#[Keywords]break#;
		#[Keywords]case #7:printf(#[Fields]"seven\n"#);#[Keywords]break#;
		#[Keywords]case #8:printf(#[Fields]"eight\n"#);#[Keywords]break#;
		#[Keywords]case #9:printf(#[Fields]"nine\n"#);#[Keywords]break#;
		#[Keywords]default#:printf(#[Fields]"error\n"#);
	#}
#}
[/code]
程序执行结果如下：
[code=java]
input integer number(<10): 3 #[Tags]/*输入数字3*/#
three #[Tags]/*程序输出结果*/#
input integer number(<10): 11 #[Tags]/*输入数字11*/#
error #[Tags]/*程序输出结果*/#
[/code]