在头文件<stdio.h>中定义了输入输出函数，类型和宏。这些函数、类型和宏几乎占到标准库的三分之一。
下面给出头文件<stdio.h>中声明的函数以及功能简介，见下表。
<stdio.h>中声明的函数
[code=java]
函数定义, 函数功能简介
FILE *fopen(#[Keywords]char #*filename, #[Keywords]char #*type), 打开一个文件
FILE *fropen(#[Keywords]char #*filename, #[Keywords]char #*type,FILE *fp), 打开一个文件，并将该文件关联到fp指定的流
#[Keywords]int #fflush(FILE *stream), 清除一个流
#[Keywords]int #fclose(FILE *stream), 关闭一个文件
#[Keywords]int #remove(#[Keywords]char #*filename), 删除一个文件
#[Keywords]int #rename(#[Keywords]char #*oldname, #[Keywords]char #*newname), 重命名文件
FILE *tmpfile(void), 以二进制方式打开暂存文件
#[Keywords]char #*tmpnam(#[Keywords]char #*sptr), 创建一个唯一的文件名
#[Keywords]int #setvbuf(FILE *stream, #[Keywords]char #*buf, #[Keywords]int #type, unsigned size), 把缓冲区与流相关
#[Keywords]int #printf(#[Keywords]char #*format...), 产生格式化输出的函数
#[Keywords]int #fprintf(FILE *stream, #[Keywords]char #*format[, argument,...]), 传送格式化输出到一个流中
#[Keywords]int #scanf(#[Keywords]char #*format[,argument,...]), 执行格式化输入
#[Keywords]int #fscanf(FILE *stream, #[Keywords]char #*format[,argument...]), 从一个流中执行格式化输入
#[Keywords]int #fgetc(FILE *stream), 从流中读取字符
#[Keywords]char #*fgets(#[Keywords]char #*string, #[Keywords]int #n, FILE *stream), 从流中读取一字符串
#[Keywords]int #fputc(#[Keywords]int #ch, FILE *stream), 送一个字符到一个流中
#[Keywords]int #fputs(#[Keywords]char #*string, FILE *stream), 送一个字符到一个流中
#[Keywords]int #getc(FILE *stream), 从流中取字符
#[Keywords]int #getchar(void), 从stdin流中读字符
#[Keywords]char #*gets(#[Keywords]char #*string), 从流中取一字符串
#[Keywords]int #putchar(#[Keywords]int #ch), 在stdout上输出字符
#[Keywords]int #puts(#[Keywords]char #*string), 送一字符串到流中
#[Keywords]int #ungetc(#[Keywords]char #c, FILE *stream), 把一个字符退回到输入流中
#[Keywords]int #fread(#[Keywords]void #*ptr, #[Keywords]int #size, #[Keywords]int #nitems, FILE *stream), 从一个流中读数据
#[Keywords]int #fwrite(#[Keywords]void #*ptr, #[Keywords]int #size, #[Keywords]int #nitems, FILE *stream), 写内容到流中
#[Keywords]int #fseek(FILE *stream, #[Keywords]long #offset, #[Keywords]int #fromwhere), 重定位流上的文件指针
#[Keywords]long #ftell(FILE *stream), 返回当前文件指针
#[Keywords]int #rewind(FILE *stream), 将文件指针重新指向一个流的开头
#[Keywords]int #fgetpos(FILE *stream), 取得当前文件的句柄
#[Keywords]int #fsetpos(FILE *stream, const fpos_t *pos), 定位流上的文件指针
#[Keywords]void #clearerr(FILE *stream), 复位错误标志
#[Keywords]int #feof(FILE *stream), 检测流上的文件结束符
#[Keywords]int #ferror(FILE *stream), 检测流上的错误
#[Keywords]void #perror(#[Keywords]char #*string), 系统错误信息
[/code]
在头文件<stdio.h>中还定义了一些类型和宏。