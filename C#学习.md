
学习资源来自于https://www.runoob.com/csharp/csharp-tutorial.html
> C#程序主要包括的部分
- 命名空间声明（Namespace declaration）
- 一个 class
- Class 方法
- Class 属性
- 一个 Main 方法
- 语句（Statements）& 表达式（Expressions）
- 注释
```
using System;
namespace HelloWorldApplication
{
   class HelloWorld
   {
      static void Main(string[] args)
      {
         /* 我的第一个 C# 程序*/
         Console.WriteLine("Hello World");
         Console.ReadKey();
      }
   }
}
```
-  using 关键字用于在程序中包含 System 命名空间。 一个程序一般有多个 using 语句。
-  namespace 声明。一个 namespace 里包含了一系列的类。HelloWorldApplication 命名空间包含了类 HelloWorld。
-  class 声明。类 HelloWorld 包含了程序使用的数据和方法声明。类一般包含多个方法。方法定义了类的行为。在这里，HelloWorld 类只有一个 Main 方法。
-  下一行定义了 Main 方法，是所有 C# 程序的 入口点。Main 方法说明当执行时 类将做什么动作。
-  Main 方法通过语句 Console.WriteLine("Hello World"); 指定了它的行为。
WriteLine 是一个定义在 System 命名空间中的 Console 类的一个方法。该语句会在屏幕上显示消息 "Hello, World!"。
- 最后一行 Console.ReadKey(); 是针对 VS.NET 用户的。这使得程序会等待一个按键的动作，防止程序从 Visual Studio .NET 启动时屏幕会快速运行并关闭。


>C#中注意的
- C# 是大小写敏感的。
- 所有的语句和表达式必须以分号（;）结尾。
- 程序的执行从 Main 方法开始。
- 与 Java 不同的是，文件名可以不同于类的名称。


> C#基本语法
- 标识符
标识符是用来识别类、变量、函数或任何其它用户定义的项目。在 C# 中，类的命名必须遵循如下基本规则：
   - 标识符必须以字母、下划线或 @ 开头，后面可以跟一系列的字母、数字（ 0 - 9 ）、下划线（ _ ）、@。
   - 标识符中的第一个字符不能是数字。
   - 标识符必须不包含任何嵌入的空格或符号，比如 ? - +! # % ^ & * 
   - 标识符不能是 C# 关键字。除非它们有一个 @ 前缀。 例如，@if 是有效的标识符，但 if 不是，因为 if 是关键字。
   - 标识符必须区分大小写。大写字母和小写字母被认为是不同的字母。
   - 不能与C#的类库名称相同。  

> C#的数据类型
- 值类型（Value types）
   - 整数类型	sbyte、byte、short、ushort、int、uint、long、ulong 和 char
   - 浮点型	float 和 double
   - 十进制类型	decimal
   - 布尔类型	true 或 false 值，指定的值
   - 空类型	可为空值的数据类型
   - 特点：
       -  1.不能从值类型派生新类型，但可以结构实现接口；
       -  2.值类型不能包含 null 值；
       -  3.每个值类型都具有一个初始化该类型的默认值的隐式默认构造函数。
- 引用类型
    - 内置的 引用类型有：object、dynamic 和 string
- 对象（Object）类型
    -  装箱：当一个值类型转换为对象类型时
     int val = 8;
     object obj = val;//整型数据转换为了对象类型（装箱）
    -  拆箱：当一个对象类型转换为值类型时
    ```
    int val = 8;
    object obj = val;//先装箱
    int nval = （int）obj;//再拆箱
    只有装过箱的数据才能拆箱
    ```
- 动态（Dynamic）类型
  声明动态类型的语法：
  dynamic <variable_name> = value;例如：dynamic d = 20;
- 字符串（String）类型
  字符串（String）类型的值可以通过两种形式进行分配：引号和 @引号。
  String str = "runoob.com";/@"runoob.com";
  string str = @"C:\Windows";==string str = "C:\\Windows";
- 指针类型（Pointer types）
  声明指针类型的语法：type* identifier;

> C#类型转换
- 隐式类型转换 - 这些转换是 C# 默认的以安全方式进行的转换, 不会导致数据丢失。例如，从小的整数类型转换为大的整数类型，从派生类转换为基类。
- 显式类型转换 - 显式类型转换，即强制类型转换。显式转换需要强制转换运算符，而且强制转换会造成数据丢失。
```
double d = 5673.74;
            int i;

            // 强制转换 double 为 int
            i = (int)d;
            Console.WriteLine(i);
            Console.ReadKey();
```
```
ToBoolean:如果可能的话，把类型转换为布尔型。
ToByte:把类型转换为字节类型。
ToChar：如果可能的话，把类型转换为单个 Unicode 字符类型。
ToDateTime：把类型（整数或字符串类型）转换为 日期-时间 结构。
ToDecimal：把浮点型或整数类型转换为十进制类型。
ToDouble：把类型转换为双精度浮点型。
ToInt16：把类型转换为 16 位整数类型。
ToInt32：把类型转换为 32 位整数类型。
ToInt64：把类型转换为 64 位整数类型。
ToSbyte：把类型转换为有符号字节类型。
ToSingle：把类型转换为小浮点数类型。
ToString：把类型转换为字符串类型。
ToType：把类型转换为指定类型。
ToUInt16：把类型转换为 16 位无符号整数类型。
ToUInt32：把类型转换为 32 位无符号整数类型。
ToUInt64：把类型转换为 64 位无符号整数类型。
```
- string 转换为int， int.Parse()
  string a = "123";     // 将a设置为字符串“123”
  int x = int.Parse(a); 


```
try
{              
}
catch (Exception)
{             
}

抛出异常具体代码
using System;
class 测试
{
    static void Main(string[] args)
    {
        try
        {
           Console.WriteLine("输入数字，将计算出它加一的答案");
           int a = int.Parse(Console.ReadLine());   //有可能会抛出异常
           Console.WriteLine("答案是{0}",++a);   //如果没有异常，程序才会进入这一步
        }
        catch (Exception)
        {
            Console.WriteLine("无法转换");  //如果捕获到异常，就说“无法转换”
        }
         Console.ReadKey();
    }
}
```

> C#中的变量定义
- 变量定义<data_type> <variable_list>;
在这里，data_type 必须是一个有效的 C# 数据类型，可以是 char、int、float、double 或其他用户自定义的数据类型。variable_list 可以由一个或多个用逗号分隔的标识符名称组成。
- 不同类型变量进行运算的问题：
  double a = 42.29;
  int b = 4229;
  double c = a + b;
  Console.WriteLine("c = {0}",c);
  Console.ReadKey();

- 静态常量（编译时常量）const
  const double a=3.14；// 正确声明常量的方法
  const int b;         // 错误，没有初始化
- 动态常量（运行时常量）readonly
  readonly int a=1;  // 声明时初始化
  readonly int b;    // 构造函数中初始化

- 在下面两种情况下：
 a、取值永久不变(比如圆周率、一天包含的小时数、地球的半径等)。
 b、对程序性能要求非常苛刻。
可以使用 const 常量，除此之外的其他情况都应该优先采用 readonly 常量。


> C#封装
- 封装 被定义为"把一个或多个项目封闭在一个物理的或者逻辑的包中"。在面向对象程序设计方法论中，封装是为了防止对实现细节的访问。
- 抽象和封装是面向对象程序设计的相关特性。抽象允许相关信息可视化，封装则使开发者实现所需级别的抽象。
   - public：所有对象都可以访问；
   - private：对象本身在对象内部可以访问；
   - protected：只有该类对象及其子类对象可以访问
   - internal：同一个程序集的对象可以访问；
   - protected internal：访问限于当前程序集或派生自包含类的类型。