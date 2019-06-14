
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

- Protected 访问修饰符
Protected 访问修饰符允许子类访问它的基类的成员变量和成员函数。这样有助于实现继承。
- Internal 访问修饰符
Internal 访问说明符允许一个类将其成员变量和成员函数暴露给当前程序中的其他函数和对象。换句话说，带有 internal 访问修饰符的任何成员可以被定义在该成员所定义的应用程序内的任何类或方法访问。


> 修饰符比较 
 - (1) Pubilc ：任何公有成员可以被外部的类访问。
 - (2) Private ：只有同一个类中的函数可以访问它的私有成员。
 - (3) Protected ：该类内部和继承类中可以访问。
 - (4) internal : 同一个程序集的对象可以访问。
 - (5) Protected internal ：3 和 4 的并集，符合任意一条都可以访问。
  

> c#方法
- 定义方法的语法
  <Access Specifier> <Return Type> <Method Name>(Parameter List)
{
   Method Body
}
例如：public int FindMax(int num1, int num2)
{
    Method Body
}
  - Access Specifier：访问修饰符，这个决定了变量或方法对于另一个类的可见性。
  - Return type：返回类型，一个方法可以返回一个值。返回类型是方法返回的值的数据类型。如果方法不返回任何值，则返回类型为 void
  - Method name：方法名称，是一个唯一的标识符，且是大小写敏感的。它不能与类中声明的其他标识符相同。
  - Parameter list：参数列表，使用圆括号括起来，该参数是用来传递和接收方法的数据。参数列表是指方法的参数类型、顺序和数量。参数是可选的，也就是说，一个方法可能不包含参数。
  - Method body：方法主体，包含了完成任务所需的指令集。

> 递归
- 一个方法可以自我调用。这就是所谓的递归

>方法中参数的类型有三种
- in型参数
int 型参数通过值传递的方式将数值传入方法中
- ref型参数
该种类型的参数传递变量地址给方法（引用传递），传递前变量必须初始化。
该类型与out型的区别在与：
 1).ref 型传递变量前，变量必须初始化，否则编译器会报错, 而 out 型则不需要初始化
 2）.ref 型传递变量，数值可以传入方法中，而 out 型无法将数据传入方法中。换而言之，ref 型有进有出，out 型只出不进。
- out 型参数
与 ref 型类似，仅用于传回结果。


> 可空类型
- ? : 单问号用于对 int,double,bool 等无法直接赋值为 null 的数据类型进行 null 的赋值，意思是这个数据类型是 NullAble 类型的。
    - int? i = 3 
      等同于
      Nullable<int> i = new Nullable<int>(3);
- ?? : 双问号 可用于判断一个变量在为 null 时返回一个指定的值。
   

> 数组
- 数组是一个存储相同类型元素的固定大小的顺序集合。数组是用来存储数据的集合，通常认为数组是一个同一类型变量的集合。
- 声明数组的语法
  - datatype[] arrayName;
    -  datatype 用于指定被存储在数组中的元素的类型
    - [ ] 指定数组的秩（维度）。秩指定数组的大小。
    -  arrayName 指定数组的名称。

- 初始化数组
  - 声明一个数组不会在内存中初始化数组。
  - 数组是一个引用类型，所以您需要使用 new 关键字来创建数组的实例。
  - double[] balance = new double[10];




> C#字符串
 - string 关键字是 System.String 类的别名。
 - String 类有以下两个属性：
    - Chars
在当前 String 对象中获取 Char 对象的指定位置。
   -  Length
在当前的 String 对象中获取字符数。

- String 类的方法
  - public static int Compare( string strA, string strB ) 
比较两个指定的 string 对象，并返回一个表示它们在排列顺序中相对位置的整数。该方法区分大小写。
  - public static int Compare( string strA, string strB, bool ignoreCase ) 
比较两个指定的 string 对象，并返回一个表示它们在排列顺序中相对位置的整数。但是，如果布尔参数为真时，该方法不区分大小写。
  - public static string Concat( string str0, string str1 ) 
连接两个 string 对象。
  - public static string Concat( string str0, string str1, string str2 ) 
连接三个 string 对象。
  - public static string Concat( string str0, string str1, string str2, string str3 ) 
连接四个 string 对象。
  - public bool Contains( string value ) 
返回一个表示指定 string 对象是否出现在字符串中的值。
  - public static string Copy( string str ) 
创建一个与指定字符串具有相同值的新的 String 对象。
  - public bool EndsWith( string value ) 
判断 string 对象的结尾是否匹配指定的字符串。
  - 更多https://www.runoob.com/csharp/csharp-string.html



> C#结构体
- 在 C# 中，结构体是值类型数据结构。它使得一个单一变量可以存储各种数据类型的相关数据。struct 关键字用于创建结构体。
结构体是用来代表一个记录
- 定义结构体
  为了定义一个结构体，您必须使用 struct 语句。struct 语句为程序定义了一个带有多个成员的新的数据类型。
  例如
```
struct Books
{
   public string title;
   public string author;
   public string subject;
   public int book_id;
}; 
```

- C#结构特点
  - 结构可带有方法、字段、索引、属性、运算符方法和事件。
  - 结构可定义构造函数，但不能定义析构函数。但是，您不能为结构定义默认的构造函数。默认的构造函数是自动定义的，且不能被改变。
  - 与类不同，结构不能继承其他的结构或类。
结构不能作为其他结构或类的基础结构。
结构可实现一个或多个接口。
  - 结构成员不能指定为 abstract、virtual 或 protected。
  - 当您使用 New 操作符创建一个结构对象时，会调用适当的构造函数来创建结构。与类不同，结构可以不使用 New 操作符即可被实例化。
  - 如果不使用 New 操作符，只有在所有的字段都被初始化之后，字段才被赋值，对象才被使用。
