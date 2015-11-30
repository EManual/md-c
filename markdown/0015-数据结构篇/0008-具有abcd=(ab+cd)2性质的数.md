代码如下：
```  
include<stdio.h>
void main()
{
    int n,a,b ;
    clrscr();
    puts("==========================================================");
    puts("||  This program will find the four figures which have  ||");
    puts("||     the characteristic as follows: abcd=(ab+cd)^2.   ||");
    puts("||            e.g., 3025=(30+25)*(30+25).               ||");
    puts("==========================================================");
    printf("\n >> There are following numbers with satisfied condition:\n\n");
    [Tags]/*四位数N的取值范围1000~9999*/
    for(n=1000;n<10000;n++)
    {
        a=n/100 ;
        [Tags]/*截取N的前两位数存于a*/
        b=n%100 ;
        [Tags]/*截取N的后两位存于b*/
        [Tags]/*判断N是否为符合题目所规定的性质的四位数*/
        if((a+b)*(a+b)==n)printf(" %d  ",n);
    }
    puts("\n\n >> Press any key to quit...");
    getch();
}
```