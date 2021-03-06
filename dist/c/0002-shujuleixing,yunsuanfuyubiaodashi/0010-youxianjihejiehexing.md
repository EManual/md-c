分为两种，即左结合性(自左至右)和右结合性(自右至左)。例如算术运算符的结合性是自左至右，即先左后右。如有表达式x-y+z则y应先与“-”号结合，执行x-y运算，然后再执行+z的运算。这种自左至右的结合方向就称为“左结合性”。而自右至左的结合方向称为“右结合性”。最典型的右结合性运算符是赋值运算符。如x=y=z,由于“=”的右结合性，应先执行y=z再执行x=(y=z)运算。Ｃ语言运算符中有不少为右结合性，应注意区别，以避免理解错误。表0.1列出了各运算符的优先级和结合性。
```  
表3-1 运算符的优先级和结合性
优先级	运算符	结合性
15	(), [ ], . , ->	右
14	!, ~, ++, --, +, -, &, *(类型名), sizeof	左
13	*, /, %	左
12	+, -	右
11	<<, >>	右
10	<, <=, >, >=	右
9	==, !=	右
8	&	右
7	^	右
6	|	右
5	&&	右
4	||	右
3	?:	左
2	=, *=, /=, %=, +=,-=, >>=, <<=, &=, ^=, |=	左
1	,	右
```