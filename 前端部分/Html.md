# HTML

文档撰写的原因：之前一直认为HTML只是超文本语言，相对比较简单，但是在实际应用中仍然会出现一些问题

参考文档：

[HTML 标签列表(字母排序) | 菜鸟教程 (runoob.com)](https://www.runoob.com/tags/html-reference.html)

[HTML（超文本标记语言） | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/HTML)

例如：

```html
<div>
    <ul>
        <li>这是一个li标签</li>
        <span>
            这是一个span标签(错误的用法)
        </span>
        <li>这是第二个li标签</li>
    </ul>
</div>
```

ul中嵌套只能li标签，不能嵌套其他标签或者文字

# 环境

Google Charm + Vscode

[VSCode前端最常用的插件（必备） - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/172177801)

下面开始正式学习！

# 1.简介

HTML(HyperText Markup Language)超文本标记语言

- HTML：定义网页内容的含义和结构
- CSS：描述网页的样式与展示效果
- JavaScript：实现网页的功能与行为

类比我的世界

| Web        | 我的世界             |
| ---------- | -------------------- |
| HTML       | 方块                 |
| CSS        | 方块的外观和布局     |
| JavaScript | 行为、动作、红石效果 |

前置准备：浏览器（Google Chrome）+编辑器（Vscode）

创建文件，.html后缀

首页命名：index.html

关于页面：about.html

# 2.标签简介

**自闭和标签**

没有结束标签

- `<br>`：表示换行。
- `<hr>`：表示水平分隔线。
- `<img>`：用于插入图像。
- `<input>`：用于创建输入字段。
- `<link>`：用于引入外部样式表或其他资源。

**双标签（容器标签）**

必须包含结束标签`</标签名称>`

- `<p></p>`：用于定义段落。
- `<h1></h1>` 到 `<h6></h6>`：用于定义标题，有不同的级别。
- `<div></div>`：用于定义一个文档中的分区或区块。
- `<span></span>`：用于标记文本的特定部分，通常用于应用样式或脚本操作。
- `<ul></ul>` 和 `<ol></ol>`：分别用于定义无序列表和有序列表。
- `<li></li>`：用于定义列表中的项目。
- `<table></table>`：用于创建表格。
- `<tr></tr>`：用于定义表格中的行。
- `<td></td>`：用于定义表格中的单元格。

# 3.页面结构

ctrl+!+回车

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

head区域：

- 定义标题
- 链接css、JavaScript等
- 。。。

body区域：

页面显示的内容

## 3.2 行级元素与块级元素

1. 行级元素（Inline elements）：
   - 行级元素在文档中水平排列，一般只占据它所包含的内容的宽度。
   - 行级元素不会独占一行，多个行级元素可以在同一行显示。
   - 通常用于包含文本片段、添加强调、创建链接等。

常见的行级元素包括：

- `<span>`：用于标记文本的特定部分，通常用于应用样式或脚本操作。
- `<a>`：用于创建链接。
- `<strong>`：用于表示强调的文本。
- `<em>`：用于表示斜体或强调的文本。
- `<img>`：用于插入图像。
- `<input>`：用于创建输入字段。

```html
<div>
	这是一个 <span>行级元素</span> 示例。请 <a href="https://www.example.com">点击这里</a> 查看更多信息。
</div>
```



2. 块级元素（Block-level elements）：

   - 块级元素会独占一行，从新行开始，并在前后都有一些额外的空间。

   - 块级元素会占据其父元素的可用宽度的整个宽度，可以设置宽度、高度、内边距和外边距。

   - 通常用于创建文档的结构、分区、标题等。

常见的块级元素包括：

- `<div>`：用于定义一个文档中的分区或区块。
- `<p>`：用于定义段落。
- `<h1>` 到 `<h6>`：用于定义标题，有不同的级别。
- `<ul>` 和 `<ol>`：分别用于定义无序列表和有序列表。
- `<li>`：用于定义列表中的项目。

```html
<div>
  <h1>这是一个块级元素示例</h1>
  <p>这是一个段落。</p>
</div>
```

# 4.标签的学习

## 4.1 标题与段落

1. 标题标签：h
   ````html
   <h1>主标题</h1>
   <h2>副标题</h2>
   <h3>子标题</h3>
   ```
   ````

2. 段落标签：p
   ````html
   <p>这是一个段落。</p>
   <p>这是另一个段落。</p>
   ```
   ````

## 4.2 a标签

`a`标签是 HTML 中的超链接元素，用于创建链接到其他页面、文档、URL 或特定位置的锚点。

`a`标签的属性

- `href`：指定链接的目标地址。可以是其他页面的 URL、文档的路径、外部网站的 URL，或者页面内的锚点。
- `target`：可选属性，指定链接在何处打开
  -  `_blank`（在新窗口或标签页中打开）
  -  `_self`（在当前窗口或标签页中打开

## 4.3列表标签

1. 无序列表（Unordered List）：
   - 无序列表用于表示一组项目，这些项目之间没有特定的顺序。
   - 在 HTML 中，可以使用 `<ul>` 标签创建无序列表，每个项目使用 `<li>` 标签表示。

```html
<ul>
  <li>项目1</li>
  <li>项目2</li>
  <li>项目3</li>
</ul>
```

2. 有序列表（Ordered List）：

   - 有序列表用于表示一组项目，这些项目按照特定的顺序排列。

   - 在 HTML 中，可以使用 `<ol>` 标签创建有序列表，每个项目使用 `<li>` 标签表示。

```html
<ol>
  <li>项目1</li>
  <li>项目2</li>
  <li>项目3</li>
</ol>
```

## 4.4 表格标签

**案例**

```html
<table>
  <tr>
    <th>姓名</th>
    <th>年龄</th>
    <th>专业</th>
  </tr>
  <tr>
    <td>John Doe</td>
    <td>25</td>
    <td>计算机科学</td>
  </tr>
  <tr>
    <td>Jane Smith</td>
    <td>22</td>
    <td>市场营销</td>
  </tr>
  <tr>
    <td>David Johnson</td>
    <td>28</td>
    <td>工程管理</td>
  </tr>
</table>
```



**在 HTML 中，用于创建表格的主要标签是 `<table>`、`<tr>`、`<th>` 和 `<td>`**

1. `<table>`标签

   - `<table>` 标签用于创建表格。

   - 它是表格的顶级容器，所有的表格内容都应该包含在 `<table>` 标签中。

```html
<table>
  <!-- 表格内容 -->
</table>
```

2. `<tr>`标签

   - `<tr>` 标签用于创建表格中的行（row）。

   - 行是由一个或多个单元格组成的水平行。

   - `<tr>` 标签必须包含在 `<table>` 标签中。

<table>
  <tr>
    <!-- 行中的单元格内容 -->
  </tr>
</table>

3. `<th>`标签
   - `<th>` 标签用于创建表格中的表头单元格（header cell）。
   - 表头单元格包含表格的标题或列的标题。
   - 默认情况下，表头单元格会加粗并居中显示。
   - `<th>` 标签必须包含在 `<tr>` 标签中。

```html
<table>
  <tr>
    <th>表头1</th>
    <th>表头2</th>
  </tr>
</table>
```

4. `<td>` 标签：

   - `<td>` 标签用于创建表格中的数据单元格（data cell）。

   - 数据单元格包含表格中的实际数据。

   - `<td>` 标签必须包含在 `<tr>` 标签中。

```html
<table>
  <tr>
    <td>数据1</td>
    <td>数据2</td>
  </tr>
</table>
```

## 4.5 表单标签

```html
<form action="/submit" method="post">
  <div>
    <label for="username">用户名：</label>
    <input type="text" id="username" name="username" placeholder="请输入用户名" required>
  </div>
  <div>
    <label for="password">密码：</label>
    <input type="password" id="password" name="password" placeholder="请输入密码" required>
  </div>
  <div>
    <label>性别：</label>
    <input type="radio" name="gender" value="male" id="male">
    <label for="male">男</label>
    <input type="radio" name="gender" value="female" id="female">
    <label for="female">女</label>
  </div>
  <div>
    <label for="country">国家：</label>
    <select id="country" name="country">
      <option value="china">中国</option>
      <option value="usa">美国</option>
      <option value="uk">英国</option>
    </select>
  </div>
  <div>
    <label for="message">留言：</label>
    <textarea id="message" name="message" rows="4" cols="30" placeholder="请输入留言"></textarea>
  </div>
  <div>
    <input type="checkbox" name="agree" id="agree" required>
    <label for="agree">我同意条款和条件</label>
  </div>
  <div>
    <button type="submit">提交</button>
    <button type="reset">重置</button>
  </div>
</form>
```

在 HTML 中，用于创建表单的主要标签是 `<form>`，并且还有其他用于收集用户输入的表单元素

1. `<form>` 标签：

   - `<form>` 标签用于创建表单。

   - 表单是用于收集用户输入的交互式区域。

   - 所有的表单元素都应该包含在 `<form>` 标签中。

2. `<input>` 标签：

   - `<input>` 标签用于创建各种类型的输入字段。

   - 根据 `type` 属性的不同值，可以创建文本输入框、密码输入框、复选框、单选按钮等不同类型的输入字段。

```html
<input type="text" name="username" placeholder="请输入用户名">
<input type="password" name="password" placeholder="请输入密码">
<input type="checkbox" name="agree" id="agree">
<label for="agree">我同意条款和条件</label>
<input type="radio" name="gender" value="male" id="male">
<label for="male">男</label>
<input type="radio" name="gender" value="female" id="female">
<label for="female">女</label>
```

3. `<textarea>` 标签：

   - `<textarea>` 标签用于创建多行文本输入框。

   - 用户可以在文本域中输入多行文本，例如评论或消息。

```html
<textarea name="message" rows="4" cols="30" placeholder="请输入消息"></textarea>
```

4. `<select>` 和 `<option>` 标签：

   - `<select>` 标签用于创建下拉列表框。

   - `<option>` 标签用于定义下拉列表中的选项。

```html
<select name="country">
  <option value="china">中国</option>
  <option value="usa">美国</option>
  <option value="uk">英国</option>
</select>
```

5. `<button>` 标签：
   - `<button>` 标签用于创建按钮。
   - 可以使用 `<button>` 标签创建提交按钮、重置按钮或普通按钮。

```html
<button type="submit">提交</button>
<button type="reset">重置</button>
<button type="button">点击我</button>
```

## 4.6 按钮标签

在 HTML 中，用于创建按钮的主要标签是 `<button>`。`<button>` 标签可以用来创建多种类型的按钮，如提交按钮、重置按钮、普通按钮等

1. 提交按钮：
   - 提交按钮用于提交表单数据到服务器进行处理。
   - 使用 `type="submit"` 属性来指定按钮类型为提交按钮。

```html
<button type="submit">提交</button>
```

2. 重置按钮：

   - 重置按钮用于将表单字段的值重置为默认值。

   - 使用 `type="reset"` 属性来指定按钮类型为重置按钮。

3. 普通按钮：

   - 普通按钮用于执行自定义的 JavaScript 函数或操作。

   - 使用 `type="button"` 属性来指定按钮类型为普通按钮。

```html
<button type="button" onclick="myFunction()">点击我</button>
```

## 4.7 图像标签

在 HTML 中，用于显示图像的主要标签是 `<img>`。`<img>` 标签允许	在网页上嵌入图像，并通过指定图像的 URL 来引用图像文件

1. `src` 属性：

- `src` 属性用于指定图像文件的 URL。
- URL 可以是相对路径或绝对路径，指向图像文件的位置。

```html
<img src="path/to/image.jpg" alt="图像描述">
```

2. `alt` 属性：

- `alt` 属性用于提供图像的替代文本，用于辅助技术和当图像无法显示时显示。
- `alt` 属性应该提供对图像的简明描述。

```html
<img src="path/to/image.jpg" alt="美丽的风景">
```

3. `width` 和 `height` 属性：

   - `width` 和 `height` 属性用于指定图像的显示宽度和高度（以像素为单位）。

   - 这些属性可以用来调整图像在页面上的尺寸，但最好保持图像的原始比例。

```html
<img src="path/to/image.jpg" alt="图像描述" width="300" height="200">
```

4. `title` 属性：

   - `title` 属性用于提供有关图像的额外信息，当用户将鼠标悬停在图像上时会显示为工具提示。

   - `title` 属性可以用于提供进一步的解释或描述。

```html
<img src="path/to/image.jpg" alt="图像描述" title="点击以放大">
```

