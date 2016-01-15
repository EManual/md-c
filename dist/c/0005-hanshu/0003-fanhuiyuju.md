C语言中的返回语句有下列形式：

```  
return 表达式;
```

返回语句的作用有两个，一是把控制返回给调用者(函数)，另一是向调用者传递有关信息。例如：

```  
retrun;
return -1;
retrun x+y;
retrun ++x;
```

上例中第一个语句没有返回任何值，只是把控制返回给了调用者，而其余的既返回了控制，又返回了值。

一个函数中的返回语句可以有一个、多个或没有，若在执行一个函数时没遇到return语句，则从这个函数的末尾一个语句后返回，或者可以认为函数体大括号“}”前有一个无形的return语句(不带返回值)。

所有非空值的函数都会返回一个值。我们编写的程序中大部分函数属于三种类型。第一种类型是简单计算型－函数设计成对变量进行运算，并且返回计算值。计算型函数实际上是一个“纯”函数，例如sqrt函数（开方运算）和sin函数（正弦运算）。第二类函数处理信息，并且返回一个值，仅以此表示处理的成功或失败。例如write函数，用于向磁盘文件写信息。如果写操作成功了，write函数返回写入的字节数，当函数返回-1时，标志写操作失败。最后一类函数没有明确的返回值。实际上这类函数是严格的过程型函数，不产生值。
对于具有返回值的函数，调用者可以使用这个值，也可以不使用这个值。例如程序段：

```  
getchar();
c = getchar();
```

其中第一个getchar执行一次就得到一个字据，但程序不对这个返回值做任何处理，而把接下去第二个getchar得到的字符赋给变量c。
例0.15：编写求1+2+…+n的函数。

```  
double fsum (int n)
{
	int i;
	double tempsum=0;
	if(n<=0)
	{
		printf("Input number is error! %d<=0\n",n);
		return -1.0;
	}
	for(i=1;i<=n;i++)
		tempsum+=i;
	return tempsum;
}
```

在上面的程序中，double fsum(int n)是函数的首部，其中fsum是函数名，在它前面的double是类型名，用来说明函数返回值的类型是双精度型。在本例中只有一个形式参数n，其类型为int。

函数体中，除形式参数外，用到的其它变量必须在说明部分进行定义，这些变量(包括形式参数)，只在函数被调用时才临时开辟存储单元、当退出函数时，这些临时开辟的存储单元全被释放掉，因此，这种变量只在函数体内部起作用，与其它函数体中的变量互不相关，它们可以和其它函数中的变量同名。函数体中的说明部分，就像在main函数中那样，总是放在函数体中所有可执行语句之前。fsum函数中定义了一个int类型的变量i、一个double类型的变量tempsum，当退出fsum函数后，这些变量，包括形式参数n所占的存储单元都不再保留。

fsum函数中有两处出现return语句，函数中通过for循环进行连加，求出1+2+…+n，并把结果放在变量tempsum中，最后的return tempsum语句，使流程返回到调用该函数的地方，并把所求得的的值带回，fsum函数的if语句中还有一个语句return -1.0；，在此表示如果n的值小于0，则不能求连加，在退出函数时同时返回-1.0作为出错的标志。