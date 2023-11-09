1.内存管理
	堆的管理： malloc calloc realloc free
			错误码， perror
2.存储类：
	auto      ：修饰局部变量。默认省略不写
	register ：修饰局部变量。
	static     ：
			static  修饰局部变量：形成静态变量
			static  修饰全局变量
			static  修饰函数

多文件编译：
	编译： 四个步骤： 预处理 编译 汇编 链接 
只有在链接之中才有多文件之间的交互
前三个过程中不会管函数存不存在，只有在链接才回去寻找
	
extern    ：
		extern 全局变量
		extern 函数