## 二、printf和scanf

printf和scanf一般用来进行控制台的输出和输入，这两个函数都存在于stdio库里。

```c
#include <stdio.h>

int main() {
    int i = 0;
    do {
        scanf("%d", &i);
        printf("输入为：%d\n", i);
    } while (i != 0);
    
    return 0;
}
```

printf、scanf中的转换格式指定符：

* 字符类型：%c
* 整型：char、short、int => %d、long => %ld、unsigned char、unsigned short、unsigned int => %u、unsigned long => %lu
* 浮点型：float => %f、double => %lf
* 布尔类型：%d
* 内存地址：%p
* 字符串：%s

```c
#include <stdio.h>
#include <stdbool.h>

int main() {
    char c = 'A';
    printf("%c\n", c); // A
    
    int i1 = 10;
    long i2 = 20;
    unsigned int i3 = 30;
    unsigned long i4 = 40;
    printf("开始%03d结束\n", i1); // 开始010结束，%03d代表占用3个字符位置，且默认靠右对齐，空白的位置用0补齐
    printf("开始%-3ld结束\n", i2); // 开始20 结束，%-3ld代表占用3个字符位置，且靠左对齐，空白的位置用 补齐
    printf("开始%u结束\n",  i3); // 开始30结束
    printf("开始%lu结束\n", i4); // 开始40结束
    
    float f = 3.1415926897;
    double d = 3.1415926897;
    printf("%.15f\n", f); // 3.141592741012573，%.15f代表四舍五入保留15位小数
    printf("%.15lf\n", d); // 3.141592689700000
    
    bool b = true;
    printf("%d\n", b); // 1
    
    char *name = "Jack";
    printf("%p\n", name); // 0x100003fa5
    
    char name1[] = "Jack";
    printf("%s\n", name1); // Jack
    
    return 0;
}
```

