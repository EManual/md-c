本节中数据的输入以终端键盘为处理对象，即程序接收用户从键盘输入的数据。

#### 字符输入函数getchar

与putchar函数相对应，getchar函数的作用是接收从键盘输入的单个字符。当程序执行到该函数时，将等待用户从键盘输入一个字符，然后再继续后续程序的执行。其一般调用形式如下：

```  
char a;
getchar (a);
```

例0.5：下面给出了使用getchar函数的程序。

```  
include "stdio.h"
main()
{
	char a;
	a=getchar();
	putchar(a);
	printf("\n");
}
```

程序执行到getchar后将等待用户输入字符，然后putchar再将刚才输入的字符显示到屏幕上。

#### 格式输入函数scanf

getchar函数只能接收从键盘输入的单个字符，与printf函数相对应，scanf函数是具有格式控制的输入函数，可以用于输入C语言中任意类型的数据，而且可以一次同时输入多个相同类型或不同类型的数据。共一般调用形式如下：
scanf(格式控制，输入地址表列);
该函数括号内包括两部分：

#### 1、格式控制

格式控制是用双引号括起来的字符串，也称为“格式控制转换字符串”，其中包括格式说明和需要原样输入的普通字符。格式说明部分中“％”和格式控制字符组成，如％c、％d和％f等，共作用是将输入的数据转换成指定的格式后存入到地址表列所指向的变量中。
scanf函数中使用的格式字符与printf函数中使用的一样。

#### 2、输入地址表列

输入地址表列用以指明键盘输入数据的保存位置，即输入对象，它必须是地址形式，如变量的地址。如果有多个输入对象，则多个输入地址之间用逗号隔开。在C语言中变量的地址可以内取地址运算符“＆”得到，如变量a的地址可写成&a。关于地址概念的详细介绍，请参见后续“指针”一节。
例0.6：利用scanf函数，从键盘中输入2个整数，1个浮点数和一个字符，代码如下：

```  
include "stdio.h"
main()
{
	int i,j;
	float c;
	char a;
	scanf("i=%d,j=%d,%f,%c",&i,&j,&c,&a);
	printf("i=%d,j=%d, f=%f,a= %c\n",i,j,c,a);
}
```

上述程序执行到scanf函数时，需要用户从键盘输入数据，才能继续执行后续语句。程序执行结果如下：

```  
i=2,j=3,1.5,c [Tags]/*此处为用户输入数据*/
i=2,j=3, f=1.500000,a= c [Tags]/*程序输出结果*/
```

在使用scanf函数时还应注意以下问题：
1. scanf函数中的每个输入格式控制符，都必须在输入参数表列中有一个输入对象与之对应，且格式符必须与相应的输入对象类型一致，即把输入数据保存到对应的输入对象中。
2. 当格式控制符之间没有任何字符时，在输入数据时，键盘输入的数据之间可以用空格、回车或Tab键间隔。如果格式符之间包含其它字符，则应输入与这些字符相同的字符作为间隔，如上例中的“i=2”、“j=3”和“，”，即格式符之间的其它字符必须原样输入，否则不能把数据存入相应的输入对象。
应该注意，在输入字符型数据时，由于任何字符都能作为有效字符输入，因此，不必用空格、回车或Tab键作为间隔。
3. 可以在格式符的前面指定输入数据所占的宽度，系统能自动按此宽度裁取相应宽度的数据。如：

```  
scanf("%3d,%2d",&i,&j);
```

当键盘输入12345时，系统能自动地把123赋给变量i，将345赋给变量j。这种方式也可用于字符型数据的输入，但不能用于实型数据的输入。如

```  
scanf("%6.3f",&c)
```

是非法的，不能企图通过程盘输入123456而使f的值为120.456，即输入实型数据时不能规定精度。
4. 需要再次强调的是，用以指明输入对象的输入地址表列必须是地址形式，如要把键盘输入保存到变量中，则要用变量的地址，而不是变量名。如果只写变量名，编译不会出错，但程序执行时，就会出现混乱。请在学习后续章节中的指针等内容后，仔细加以体会。
例0.7：编写程序，输入长方体的长、宽、高，计算长方体的表面积和体积。

```  
include "stdio.h"
main()
{
	float length,width,height;
	float area,volume;
	printf("Input length,width,height:\n");
	scanf("%f,%f,%f",&length,&width,&height);
	area=2*(length*width+length*height+width*height); /*计算长方体表面积*/
	volume=length*width*height; /*计算长方体体积*/
	printf("%f,%f,%f\n",length,width,height);
	printf("The surface area is %f, volume is %f\n",area,volume);
}
```

执行到scanf函数时，需要用户从键盘输入长方体的长、宽、高，然后计算相应的表面积和体积，最后输出输入的长、宽、高以及表面积和体积。