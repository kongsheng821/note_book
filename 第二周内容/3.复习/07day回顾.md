1.函数：
	函数的定义：
		char fun (int a)
		{
			return ‘a'；
		}
#返回值不是必要的，要根据具体功能，需不需要返回值到main函数里面

(返回）void fun (void)（输入）
{
	

}
	函数声明：
		void fun(void);
	函数调用：
		void fun（void）
		{
			
		}
调用：
	void fun (void);
	{
	
	}

fun()；

编译过程：
在内存中运行，内存中有个空间叫栈，fun函数调用完后就释放。
![[1698888200502.png]]

2.数组：
	专门用来存储同一类型的数据的
	short arr[50];
	arr [0];
	short brr [40] = {1,2,3};//完全初始化

================================================
作业
![[af7433a6d2ec86dc5ec46dc69ccc45b.png]]
画菱形：
要先分析关系
![[d11d121865e73eaaac39457ec378ca6.png]]
![[1698890591129.png]]
考察程序在进行运算的时候会发生什么
类型转换，括单术，所以当前算术优先，index -1优先判断
因为index为无符号长整型，无符号长整型只有正数，所以此时，1与index进行算术先要进行格式转化，1为int类型，转化为无符号长整形，但是因为index也是无符号长整形，