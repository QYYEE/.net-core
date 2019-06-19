> 数据传递

- 数据传递可以使用的形式：ViewData、ViewBag、cache、TempData、Session、Model
- ViewData是按照键值对和索引器，支持任意类型
```
ViewData["IntTestData"] = 100;
ViewData["StringTestData"] = "这是个字符串";
```
- ViewBag是动态类型是ViewData的封装、动态属性
  ```
  ViewBag.IntTestData = 100;
  ViewBag.StringTestData = "这是个字符串";
  绑定
  @ViewData["IntTestData"]
    @ViewBag.StringTestData
  ```
>  数据绑定

- Razor语法
   - 表示C#代码块或语句
   - @*注释*@
   - C#代码可与Html混合

- 传输列表数据
   - 在控制器内创建List<>
    ```
      List<string> IsData = new List<string>();
            IsData.Add("第一行数据");
            IsData.Add("第二行数据");
            IsData.Add("第三行数据");
            IsData.Add("第四行数据");
    ```
    - 在视图内绑定
      <ul>
    @foreach (var item in ViewBag.ListData)
    {
        <li>@item</li>
    }
    </ul>

> 表单
- 在视图内创建表单
```
<form action="/test/checkuser" method="post">
   用户名:<input type="text" name="username"/>
   密码:<input type="password" name="userpassword"/>
   <input type="submit" value="登录">
</form>
```
另一种方法
```
用户名1:@Html.TextBox("username1")
密码1:@Html.Password("userpassword1")
```
> 数据和表单的结合

- 使用@语句方式把数据复制给表单数据属性：
```
<input value="@ViewBagData"/>
```
- 使用提供方法重载
  ```
  @Html.TextBox(name,value,format，htmlattributes)
  ```
> 使用Model传递数据
- Test1Controller.cs处代码
```
public IActionResult Index()
        {
            UserModel model = new UserModel()
            //model实例化
            {
                UserName = "Test",
                TrueName = "张三",
                TelePhone="1888999932"};
            return View(model);
        }

public class UserModel//创建UserModel类
        {
            public string UserName { get; set; }

            public string TrueName { get; set; }
            public string TelePhone { get; set; }
        }
```
- 视图页面代码
```
<body>
    <table>
        <tr>
            <td>用户名：</td>
            <td>@Model.UserName</td>
        </tr>
        <tr>
            <td>真实姓名：</td>
            <td>@Model.TrueName</td>
        </tr>
        <tr>
            <td>电话号码：</td>
            <td>@Model.TelePhone</td>
        </tr>
    </table>
</body>
```
- 视图提供Model属性
- Model是一个动态类型，类型取决于传递数据类型

> 强类型视图
- 强类型Model是一个设计时就能确定具体的数据类型，而不是运行时确定的。
- 强类型Model能提供设计时的智能提示。
- 强类型Model能方便数据绑定及数据验证。

> 强类型视图定义方法
- Model关键字使用
   - 必须在视图第一行定义
   -@model后面跟着数据类型名称
- Model属性的类型就是@model标识的类型
- 生成表单：
```
@Html.TextBoxFor(m=>m.UserName);
@Html.TextBoxFor(lamel表达式)
```

> 强类型Model数据绑定
- HtmlHelper绑定
   - @Html.XXXXFor(m=>m.Attribute)
- DisplayNameAttribute与Html.LableFor
```
在定义属性的时候的前面填写[DisplayName("用户名")]
在视图页面显示时代码为@Html.LabelFor(m =>m.TrueName)

```

> 母版页

- 实现多个视图共享，减少编码量
- 便于系统维护，共享部分内容修改，只需改一个地方即可
- 母版页使用方法
   - 跟普通视图创建一样
   - @renderbody（）输出子页面内容
   - 在子页面中使用Layout属性指定母版页
   - @rendersection实现子页面内容个性化，这种可以达到共享内容最大化
