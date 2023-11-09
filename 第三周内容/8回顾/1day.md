回顾：
内存映射：
		虚拟内存 ：
		x86 ：
				0x00000000  ~0x08048000 ： 未使用区域    
				//int \*p;     \*p  //出现段错误
				//修改：    int \*p = NULL;//让他不是野指针

>.text 代码区  ：程序指令集 （main 其他函数）
>.rodata 常亮区 ： char  \*p = "i  love u";//不能改变
>.data  已初始的全局或者静态变量
>.bss    未初始化的全局或者静态变量
>heap  堆  （malloc calloc realloc free)
>stack  栈



#野指针不要做解引用操作！

内存管理：