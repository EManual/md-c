逻辑运算符主要用于关系表达式所构成的条件的复合，条件的复合从根本上来说有三种：第一种是“两个条件都成立”，这就是两个条件的“与”运算；第二种是“两个条件至少有一个成立”，这就是两个条件的“或”运算；还有一种是“某个条件不成立”，这就是一个条件的“非”运算，它们在C语言中分别用运算符“&&”、“||”和“!”表示。

逻辑运算符的运算对象是简单数据类型（除数组和结构外的任何类型），“&&”、“||”是双目运算符，“!”是单目运算符。它们的运算结果是int型的，一般说来只有“0”和“1”两个值。对于“&&”，计算时只有当两个运算对象都不为0时表达式的值为1，其他情况表达式的值都为0；对于“||”，计算时只有当两个运算对象都为0时表达式的值为0，其他情况表达式的值都为1。

“&&”和“||”还有一个特别的性质，它们是严格从左至右进行运算的，当运算到一定程度，表达式的值可以被确定时，就不再运算下去。例如，在计算表达式

```  
((y=3)>4)&&((y=5)<7)
```

时，表达式(y＝3)的值为3，显然((y＝3)＞4)的值为0，对于“&&”，计算时只有当两个运算对象只要一个为0时表达式的值即为0，此时表达式的值已经确定，所以就不对((y=5)＜)7求值了，执行此表达式后y的值为3而不为5。