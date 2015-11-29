函数原型：char *strdup(char *str); 
头文件：#include<stdlib.h>
是否是标准函数：是
函数功能：将字符串拷贝到新分配的空间位置，也就是将str拷贝到一块新分配的存储空间，其内部使用动态分配内存技术实现的，分配给字符串的空间来自于当前所用内存模式制定的堆。
返回值：返回指向含有该串拷贝的存储区
例程如下： 应用strdup将字符串拷贝到新建位置处。
[code=java]
#include <stdio.h> 
#include <string.h>
#[Keywords]int #main(void) 
{ 
    #[Keywords]char #*src=#[Fields]"This is the buffer text"#;
    #[Keywords]char #*dest;
    #dest=strdup(src);
    #[Keywords]if#(!strcmp(src,dest))
        #printf(#[Fields]"Copy success\n%s\n"#,dest);
   #[Keywords] else#
        #printf(#[Fields]"Copy failure"#);
    #free(dest);
    #getch();
    #[Keywords]return #0;
#} 
[/code]
[color=blue]例程说明：
（1）首先，程序声明了两个字符串并给第一个字符串赋于初值，此时并未给字符串dest分配任何空间。
（2）程序通过调用strdup将字符串拷贝到新建位置处，通过动态分配内存技术将新分配一个与字符串src大小相同的存储区并完成字符串的复制工作，然后返回该存储区并让dest指向该区域。
（3）程序通过调用strcmp比较复制前后的字符串，如果复制成功而这应当相同，函数返回值为零，并打印拷贝结果。
（4）由于新分配的存储区是通过动态分配内存技术实现的，因此在程序退出之前要将分配的存储区显示的释放。
本例程的运行结果是：
[code=java]
Copy success
This is the buffer text
[/code]
注意：本例程中，初学者往往会忽视释放动态分配存储区的操作，虽然表面看起来似乎对程序没有什么影响，但实际上不对存储区进行回收会造成内存泄漏，在一些大程序会造成致命的后果。