回顾：
		结构体
		struct {int a; int y}xx;
		struct point {int a; int y}yy;(创建了一个标签，标签不能重复使用，创建好了就可以用它去定义变量)
		struct point zz;

取别名：
		typedef struct  {int a; int y;}p_t;
		p_y a;(变量名字可以和成员名字一样)
		a.x = 10;
		(&a)->y = 20;(取结构体内的成员变量)
		p_t b = {10,20};
		p_t c  ={
			.y = 30,
		};
p_t z = {
	x : 60;
}

#pragma pack(n)  n: 2^0 2^1 2^2 2^3

宏 ：
	带参数的
	不带参数的

作业：
``c
9、有以下程序：
#include <stdio.h>
#define MIN(x,y) （(x)<(y)?(x):(y)）

main()
{
	int i,j,k;
	i=10;j=15;k=10\*MIN(i,j);printf("%d\n",k);
}
程序的运行结果是
15       100       10        150
``
