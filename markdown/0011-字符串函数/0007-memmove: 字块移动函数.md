函数原型：void *memmove(void *destin, void *source, unsigned n)
头文件：#include<string.h>
是否是标准函数：是
函数功能：从source所指的对象中复制n个字符到destin所指的对象中。与memcpy不同的是，当对象重叠时，该函数仍能正确执行。
返回值：destin
例程如下：利用函数memmove进行字符块的移动
[code=java]
#include <stdio.h> 
#include <string.h> 
#[Keywords]int #main(void) 
{ 
   #[Keywords]char #*s = #[Fields]"#####"#;
   #[Keywords]char #*d = #[Fields]"This is a test #[Keywords]for #memcpy function"#;
   #[Keywords]char #*ptr; 
   #printf(#[Fields]"destination before memmove: %s\n"#, d);
   #ptr = memmove(d, s, strlen(s));
   #[Keywords]if #(ptr) 
      #printf(#[Fields]"destination after memmove:  %s\n"#, d);
   #[Keywords]else #
      #printf(#[Fields]"memcpy failed\n"#);
   #[Keywords]return #0; 
#}
[/code]
[color=blue]例程说明：
（1）首先定义两个字符串s和d，并赋初值，且d的长度大于s。
（2）显示字符串d的原始内容。
（3）通过函数memmove将字符串s复制到字符串d中，并返回字符串d的首指针。
（4）如果拷贝成功，再次显示字符串d的内容。
本例程的运行结果为：
[code=java]
destination before memmove: This is a test for memcpy function
destination after memmove:  ##########test for memcpy function
[/code]
注意：
与函数memcpy不同的是，当对象重叠时，该函数仍能正确执行。例如下面这个例子：
[code=java]
#include <string.h> 
#include <stdio.h> 
#[Keywords]int #main(void) 
{ 
  #[Keywords]char #*d = #[Fields]"1234567890"#;
  #[Keywords]char #*p;
  #p=d+3;
  #printf(#[Fields]" %s\n"#, d);
  #memmove(p, d, 6);
  #printf(#[Fields]" %s\n"#, d);
  #[Keywords]return #0; 
#}
[/code]
虽然复制的字符串在d和p之间又重叠，但本段程序的运行结果为：
[code=java]
1234567890
1231234560
[/code]
显然这是期望得到的结果。
这是因为函数memmove的复制行为类似于先从source对象中复制n个字符到一个与source和destin都不重合的含n个字符的临时数组中作为缓冲，然后从临时数组中再复制n个字符destin所指的对象中。
就本段程序而言，memmove先将字符串“123456”复制到一个临时数组中，再将它复制到以p为首地址的字符串中。