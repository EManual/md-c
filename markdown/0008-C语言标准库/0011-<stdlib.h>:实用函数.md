在头文件<stdlib.h>中声明了一些实现数值转换，内存分配等类似功能的函数。下面给出头文件<stdlib.h>中声明的函数以及功能简介，见下表。
<stdlib.h>中声明的函数
[code=java]
函数定义, 函数功能简介
#[Keywords]double #atof(const #[Keywords]char #*s), 将字符串s转换为double类型
#[Keywords]int #atoi(const #[Keywords]char #*s) , 将字符串s转换为int类型
#[Keywords]long #atol(const #[Keywords]char #*s), 将字符串s转换为long类型
#[Keywords]double #strtod (const char*s,#[Keywords]char #**endp) , 将字符串s前缀转换为double型
#[Keywords]long #strtol(const char*s,#[Keywords]char #**endp,#[Keywords]int #base), 将字符串s前缀转换为long型
unsinged #[Keywords]long #strtol(const char*s,#[Keywords]char #**endp,#[Keywords]int #base), 将字符串s前缀转换为unsinged long型
#[Keywords]int #rand(void), 产生一个0~RAND_MAX之间的伪随机数
#[Keywords]void #srand(unsigned #[Keywords]int #seed) , 初始化随机数发生器
#[Keywords]void #*calloc(size_t nelem, size_t elsize), 分配主存储器
#[Keywords]void #*malloc(unsigned size), 内存分配函数
#[Keywords]void #*realloc(#[Keywords]void #*ptr, unsigned newsize), 重新分配主存
#[Keywords]void #free(#[Keywords]void #*ptr), 释放已分配的块
#[Keywords]void #abort(void), 异常终止一个进程
#[Keywords]void #exit(#[Keywords]int #status), 终止应用程序
#[Keywords]int #atexit(atexit_t func), 注册终止函数
#[Keywords]char #*getenv(#[Keywords]char #*envvar), 从环境中取字符串
#[Keywords]void #*bsearch(const #[Keywords]void #*key, const #[Keywords]void #*base, size_t *nelem, size_t width, int(*fcmp)(const #[Keywords]void #*, const *)), 二分法搜索函数
#[Keywords]void #qsort(#[Keywords]void #*base, #[Keywords]int #nelem, #[Keywords]int #width, #[Keywords]int #(*fcmp)()), 使用快速排序例程进行排序
#[Keywords]int #abs(#[Keywords]int #i), 求整数的绝对值
#[Keywords]long #labs(#[Keywords]long #n), 取长整型绝对值
div_t  div(#[Keywords]int #number, #[Keywords]int #denom), 将两个整数相除, 返回商和余数
ldiv_t ldiv(#[Keywords]long #lnumer, #[Keywords]long #ldenom), 两个长整型数相除, 返回商和余数
[/code]
有关上面列出的这些标准实用函数的功能、用法、例程等。