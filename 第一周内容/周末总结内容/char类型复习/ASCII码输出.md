个人总结：
	在想要输出ASCII码的时候，需要将格式转化为十进制的整型数据。
	1.疑问：为什么要是转化为十进制整型数据？
	1.解惑：ASCII码中的字符编码是使用十进制数表示的
ASCII码使用7位二进制数来对字符进行编码,一共可以表示128(2^7)个字符。
- 每个编码二进制数对应一个0-127的十进制整数。
- 例如：
- 字母'A'的编码是二进制01000001,对应的十进制数是65。
- 字母'B'编码为01000010,十进制为66。
- 数字'0'编码为00110000,十进制为48。

	2.疑问2：输出ASCII码的意义是什么？
	2.解惑2：
调试字符数据 - 输出ASCII码可以检查字符变量的值是否正确,是否包含非法字符。
1. 显示不可见字符 - 如换行、回车等控制字符的ASCII码可以可视化不可见字符。
2. 数据分析 - 处理文件或网络数据时,分析其ASCII值分布情况很有帮助。
3. 字符编码转换 - 将文字转换为ASCII码可以方便不同系统传输接收。
4. 编码比较 - 比较字符串的ASCII值可以判断其编码顺序。
5. 字符位置 - 输出序号+ASCII码可以表示字符位置。
6. 格式处理 - 某些格式需要显示ASCII值而不是字符本身。（重要）
7. 编码校验 - 检测ASCII值是否在允许范围内,避免非法字符。

#include<stdio.h>
int main(){
        char a ='A';

        printf("char A : %d\n",a);

        return 0;


}

我现在想打印类型为char的“日”字
这是我写的代码：
#include<stdio.h>
int main(){
        char a ="日";
		printf("char A : %c\n",a);
		return 0;
}
输出有警告，结果也是错的
警告的原因是:

1. 原代码使用 char a = '日'; 定义了a变量。
2. 后修改为 char a = "日";,使用字符串字面量初始化。
3. 在C语言中,字符串字面量"日"的类型是char*指针。
4. 但试图赋值给char类型的a,需要把指针转成整数。
5. C语言要求这种隐式转换需要进行强制类型转换,所以报错
解决方法是:
#include<stdio.h>
int main(){
        char a[] ="日";
        printf("char A : %s\n",a);
        return 0;
}
详细过程及思路：
	因为“日”为字符串类型，因为ascii码表中没有存储汉字，所以使用字符类型是无法打印出来的。
	所以需要定义a为数组，“日”为该数组的第0个元素。
	再而格式化输出也需要将%c更改成%s，因为输出类型不同。


如果我要输出一串字符“日你仙人”该如何输出呢？
#include<stdio.h>
int main(){
        char a[] ="日你仙人";
        printf("char A : %s\n",a);
        return 0;
}
嗯哼可以正常的输出

但是如果我只想输出“日你仙”呢？
思考：我觉得“日你仙人”现在应该还是属于数组的第0位，因为并没有逗号 #，
隔开，如果想要输出自己想要的数组内的指定内容，需要将这几个字分别用逗号隔开，然后再printf中的a，改成a[1,2.,3].

测试：
代码：
#include<stdio.h>
int main(){
        char a[] ={"日,你,仙,人"};
        printf("char A : %s\n",a[1,2,3]);
        return 0;
}
报错：
ubuntu:~/Desktop/ks$ gcc char.c -o char
char.c: In function ‘main’:
char.c:5:20: warning: format ‘%s’ expects argument of type ‘char *’, but argument 2 has type ‘int’ [-Wformat=]
  printf("char A : %s\n",a[1,2,3]);
                   ~^    ~~~~~~~~
                   %d
ks21y@ubuntu:~/Desktop/ks$ ./char
段错误 (核心已转储)

