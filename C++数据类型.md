#C++数据类型笔记
***
##对象的定义  

1. 定义一个对象age，编译器会对其**分配空间（初始化）**并赋值。如下  
`int age=18;`
2. age对象进行声明（当age对象是在其他源文件中定义的时候需要声明），如下：  
`extern int age;`  
>用extern关键字，注意一个对象只能被定义一次，但可以被声明很多次。  
> 注意声明格式： extern+数据类型+对象名  
***
##作用域的嵌套  

	int main()
	{
		int age = 18;
		int people ;
		extern  int age;
		{  //作用域的嵌套
			int val1=1, val2=3;  
			//对象val1和val2的作用域从10行（声明处）开始，到12行（所在的域块）结束
			people = val1 + val2;  
			//对象people的作用域从6行开始，到14行结束。
		}
	}
***
##常量修饰符  

	const double pi = 3.1415; 
>用关键字const来保证对象pi不被修改，在此开始任何对pi进行修改的操作都是非法的  

	const int num0 = age;
>const操作必须要保证对象初始化(可以初始化变量)，否则非法  

	constexpr int num = 123;  
>关键字constexpr同样保证对象不被修改，与const不同的是，constexpr在初始化对象时，必须要给对象赋一个常量值


