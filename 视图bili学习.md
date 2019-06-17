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
