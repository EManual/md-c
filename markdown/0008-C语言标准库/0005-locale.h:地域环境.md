在<locale.h>中，定义了7个常量，一个结构，2个函数。
[color=blue]1、常量的定义
LC_ALL：传递给setlocale的第一个参数，指定要更改该locale的哪个方面。
LC_COLLATE：strcoll和strxfrm的行为。
LC_CTYPE：字符处理函数。
LC_MONETARY：localeconv返回的货币信息。
LC_NUMERIC：localeconv返回的小数点和货币信息。
LC_TIME：strftime的行为。
以上扩展成具有唯一取值的整型常数表达式，可作为setlocale的第一个参数。
NULL：由实现环境定义的空指针。
[color=blue]2、struct lconv结构
该结构用于存储和表示当前locale的设置。其结构定义如下：
[code=java]
struct lconv 
{
    #char*decimal_po#[Keywords]int #;
    #char*thousands_sep ;
    #char*grouping ;
    #char*int_curr_symbol ;
    #char*currency_symbol ;
    #char*mon_decimal_po#[Keywords]int #;
    #char*mon_thousands_sep ;
    #char*mon_grouping ;
    #char*positive_sign ;
    #char*negative_sign ;
    #[Keywords]char #int_frac_digits ;
    #[Keywords]char #frac_digits ;
    #[Keywords]char #p_cs_precedes ;
    #[Keywords]char #p_sep_by_space ;
    #[Keywords]char #n_cs_precedes ;
    #[Keywords]char #n_sep_by_space ;
    #[Keywords]char #p_sign_posn ;
    #[Keywords]char #n_sign_posn ;
#};
[/code]
[color=blue]3、函数
[code=java]
struct Iconv *localeconv(void);
[/code]
函数localeconv将一个struct Iconv类型的对象的数据成员设置成为按照当前地域环境的有关规则进行数量格式化后的相应值。
[code=java]
#[Keywords]char #*setlocale(#[Keywords]int #category,#[Keywords]char #* locale);
[/code]
函数setlocale用于更改和查询程序的整个当前地域环境或部分设置。地域环境变量由参数category(上面定义的6个常量)和locale指定。