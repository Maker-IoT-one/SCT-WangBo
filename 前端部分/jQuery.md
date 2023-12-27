学习原因：简单的静态页面已经满足不了目前项目开发的需求，需要开发一些组件（如日期选择器）秉承不重复造轮子的原则，学习jQuery，同时学习AJAX实现异步数据交互  
选择学习的课程：【3小时带你玩转jQuery+Ajax（前端开发-从入门到精通）】 https://www.bilibili.com/video/BV19L4y1v7Dy/?p=2&share_source=copy_web&vd_source=8329ea29abb0dea22c9d5a4356b1a81c

# 前置准备工作
## 下载
官网下载地址：[jQuery](https://jquery.com/)
选择下载版本：学习过程中选择开发版本development jQuery
## 版本说明
1. 完成版：jquery-x.x.x.js  --> 学习版本（学习源码，学习的最好方法）
2. 压缩版：jquery-x.x.x.min.js  --> 开发版本（压缩版，减少传输）
## 优点
1. 提供了强大的功能函数
2. 解决浏览器的兼容性问题
3. 实现丰富的UI和插件
4. 纠正错误的脚本知识
## 安装
直接引入即可
```html
<script src="jquery-3.7.1.js">
```


# 1.jQuery基础

## 1.1jQuery的使用

`$`符号在jQuery中代表对jQuery对象的引用
## 1.2DOM对象与jQuery包装集对象
原始的DOM对象只有DOM接口提供的方法和属性，通过js代码获取的对象都是DOM对象
通过jQuery获取的对象是jQuery包装集对象，简称jQuery对象
**只有jQuery对象才能使用jQuery提供的方法**
**DOM对象**
JavaScript中获取DOM对象，DOM对象只有有限的属性和方法
```js
var div = document.getElementById("testDiv")
var divs = document.getElementsByTagName("div")
```
**jQuery包装集对象**
DOM对象的扩充，在jQuery的世界中所有的对象，无论是一个还是一组，都封装成一个jQuery包装集，如获取包含jQuery包装集
```js
var jQueryObject = $("#testDiv")
```

**案例：**
```js
<div id="mydiv"></div>

<script>

    // 获取DOM对象
    var divDom = document.getElementById("mydiv");
    console.log(divDom);

  
    // 获取jQuery包装集对象
    var divJquery = $("#mydiv");
    console.log(divJquery);

  
    // Dom对象转jQuery包装集对象
    var transJquery = $(divDom);
    console.log(transJquery);

  
    // jQuery包装集对象转Dom对象
    var transDom = divJquery[0];
    console.log(transDom);

</script>
```
# 2.jQuery选择器
## 2.1基础选择器
其中前三个选择器只会选择一个第一个匹配的元素

1. id选择器：`$(#testDiv)`--->选择id为testDiv的元素
2. 元素名称选择器：`$("div")`--->选择所有所有Div元素
3. 类选择器：`$(".blue")`--->选择所有class=blue的元素
4. 选择所有元素：`$("*")`--->选择页面所有元素
5. 组合选择器：`$(#testDiv,span,blue)`--->同时选中多个选择器匹配的元素

## 2.2层次选择器
**1. 后代选择器：**`$("#parent div")`选择id为parent的元素的所有后代div元素，**包含第一代、第二代**
**2. 子代选择器 ：**`$(#parent>div)`选择id为parent的直接div元素(所有第一代元素)
3. 相邻选择器：`$(".blue+img")`选择元素的下一个指定元素，如果元素不存在，则获取不到
4. 同辈选择器：`$(".blue~img")`选择css类为blue之后的img元素

## 2.3jQuery表单选择器

1. 表单选择器：`$(":iinput")
2. 文本框选择器：`$(":text")`
3. 密码框选择器：`$(":password")`
4. 单选俺就选择器：`$(":radio")`
5. 多选按钮选择器：`$(":checkbox")`
6. 提交按钮选择器：`$(":sunmit")`
7. 图像按钮选择器：$(":image")
8. 重置按钮选择器：$(":reset")
9. 文件域选择器：$(":file")
10. 按钮选择器：$(":button")

# 3.jQuery Dom操作

## 3.1操作元素的属性

**属性的分类**

1. 固有属性：元素本身就有的属性（id、name、class、style）
2. 返回值是boolean的属性：check、selected、disable
3. 自定义属性：用户自己定义的属性

### 3.1.1获取属性

**获取属性的方法**

1. attr("属性名")
2. prop("属性名")

**区别：**

1. 固有属性，当种方法都可以获取
2. 自定义属性，attr可获取，prop不可获取
3. 返回值是bolean类型的属性
   若设置了属性attr返回具体的值，prop返回true
   若未设置属性attr返回undefined，prop返回false

**使用的方式**

`var name1 = $("#a").attr("name")`

`var name2 = $("#b").prop("name")`

### 3.1.2设置属性

**设置属性的方法**

1. attr("属性名","属性值")
2. prop("属性名","属性值")

**区别：**

1. 固有属性，当种方法都可以设置
2. 自定义属性，attr可获取，prop不可设置
3. 返回值是bolean类型的属性

**使用的方式**

`$(#a).attr("value","1")`

`$(#b).prop("value","1")`

给id为a的和b的标签设置了value = "1"的属性

也即`<input type= "checkbox" name="ch" id="a" value="1">`

### 3.1.3移除属性

1. removeAttr("属性名")

**使用的方式**

`$("#a").removeAttr("checked")`

**3.1的总结：**

**如果属性的类型是boolean则使用prop()方法、否则使用attr**

优先使用attr()方法

## 3.2操作元素的样式

### 3.2.1操作元素的样式

| 方法                     | 说明                                                         | 举例                                                         |
| ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `attr("class")`          | 获取class属性的值，即样式名称                                | `var cla = $("#id").attr("class")`                           |
| `attr("class","样式名")` | 修改class属性的值，修改样式                                  | `$(#id).attr("class","新的css名称")`                         |
| `add("样式名")`          | 添加样式名称(在原来的样式基础上添加样式，原本的样式会保留，如果出现相同的样式，以后定义的为准) | `$(#id).arrt("class","添加的css名称")`                       |
| `css()`                  | 添加具体的样式                                               | `$(#id).css("font-size","40px")`<br />`$(#id).css({"font-family":"楷体","color":"green"})` |
| `removeClass(class)`     | 移除样式名称                                                 | `$("#id").removeClass("larger")`                             |

## 3.3操作元素的内容

**表单元素：**

- `<input>`：文本输入、单选按钮、复选框、密码输入等。
- `<textarea>`：多行文本输入框。
- `<select>`：下拉列表框。
- `<option>`：下拉列表框中的选项。
- `<button>`：按钮。
- `<label>`：表单元素的标签。
- `<form>`：表单。

**非表单元素：**

- `<div>`：用于组合其他元素或分组元素。
- `<p>`：段落。
- `<h1>` 到 `<h6>`：标题。
- `<span>`：内联元素的容器。
- `<img>`：图像。
- `<a>`：链接。
- `<ul>` 和 `<li>`：无序列表。
- `<ol>` 和 `<li>`：有序列表。

### 3.3.1操作元素内容的重点：

1. **html和text用于非表单元素**
2. **val用于表单元素**

| 方法              | 说明                           | 举例                                                         |
| :---------------- | ------------------------------ | ------------------------------------------------------------ |
| html()            | 获取元素的html内容             | `var x = $("#id").html`                                      |
| html("heml,内容") | 设定元素的html内容             | `var x = $("#id").html("上海")`<br />`var x = $("#id").html("<h2>上海</h2>")` |
| text()            | 获取元素的文本内容，不包含html | `var x = $("#id").html()`                                    |
| text("text 内容") | 设置元素的文本内容，不包含html | `$("#id").text("北京")`                                      |
| val()             | 获取元素value值                | `var x = $("#id").val()`                                     |
| val("值")         | 设定元素的value值              | `var x = $("#id").val("今天天气不错")`                       |

## 3.4创建元素

在jQuery中创建元素很简单，直接使用核心函数即可

```js
$('元素内容');
$('<p>this is a paragraph!!!</p>');
```

## 3.5添加元素

**在添加元素时：**

如果元素本身不存在（新建的元素），此时会将元素追加到指定的位置

如果元素本身存在（已经有的元素），会将原来元素直接剪切设置到指定位置

### 3.5.1前追加子元素

1. 指定元素.prepend(内容)
   - 在指定元素内部的最前面追加内容
   - 内容可以是字符串、html、jQuery对象
2. $(内容).prependTo(指定元素)
   - 把内容添加到制定元素内部的最前面
   - 内容可以是字符串、html、jQuery对象

### 3.5.2后追加子元素

1. 指定元素.append(内容)
   - 在指定元素内部的最后面追加内容
   - 内容可以是字符串、html、jQuery对象
2. $(内容).append(指定元素)
   - 把内容添加到制定元素内部的最后面
   - 内容可以是字符串、html、jQuery对象

### 3.5.3前追加同级元素

1. before()
   - 在指定元素的前面追加内容

### 3.5.4后追加同级元素

1. after()
   - 在指定元素的后面追加内容

## 3.6删除元素

| 方法     | 说明                                                   | 举例                   |
| -------- | ------------------------------------------------------ | ---------------------- |
| remove() | 删除所选元素或指定的子元素，包括整个标签和内容一起删除 | `$(".green").remove()` |
| ;empty() | 清空所选元素的内容（保留标签）                         | `$(".green").empty()`  |

## 3.7遍历元素

**each()**

```
$(selectior).each(function(index,element)):遍历元素
其中index是索引
element是对应的包装集对象
```

```js
$(".gern").each(function(index,element){
    console.log(index);
    console.log(element);
})
```

