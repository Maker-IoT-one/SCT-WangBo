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



