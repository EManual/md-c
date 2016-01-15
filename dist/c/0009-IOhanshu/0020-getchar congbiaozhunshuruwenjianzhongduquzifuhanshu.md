函数原型：int getchar(void);
头文件：include<stdio.h>
是否是标准函数：是
函数功能：从标准输入文件stdin（键盘）中读取一个字符。该函数与getc类似，但参数为空，它只能从标准输入文件中读取字符，而不能读取用户自定义的文件。getchar函数在编程时多用于接收回车、换行符。
返回值：返回所读的字符，若文件结束或出错返回-1。
例程如下 应用getchar函数从标准输入设备读取下一个字符。
```  
include <stdio.h>
int main(void)
{
   int c;
   /* 从键盘上接收字符并显示，直到键入换行符为止 */
   while ((c = getchar()) != '\n')
      printf("%c", c);
   return 0;
}
```

#### 例程说明：

程序从键盘上接收字符并显示，当接收到换行符'\n'时，程序结束。