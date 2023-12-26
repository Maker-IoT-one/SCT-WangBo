# 1.尺寸操作
宽度：width
高度：height
边框：border
圆角：border-radius
内边距：padding
大小计算方式
	默认情况下，width设置百分比后（假设100%），当使用内边距padding时，会超过父级元素的大小，也即100%+padding的左右两边的边的像素大小，一般我们不希望这种情况发生，则设置属性box-sizing: boder-box;则会使计算方式改变，width和padding计算后的总和为100%
```CSS
.box{
width: 500px;
height: 280px;
border: 1px dotted grey;
border-radius:8px;
padding: 15px
box-sizing: border-box;
margin:
}
```
外边距：margin
浏览器会有默认边距，使用通配符，将浏览器的margin和padding清零
```css
*{
margin: 0;
padding: 0;
}
```
自适应居中显示（当前盒子必须有实际宽度才能生效）：
	margin-left: auto;
	margin-right: auto
	或者
	margin: 0 autol;
```CSS
.box{
margin: 30px;
margin-bottom: 50px;
margin-left: auto;
margin-right: auto
}
```
# 2.背景处理
背景颜色：background-color
背景图片：background-img: url(./bg.img)
阴影：box-shadow: 5px 5px 6px grey;
	水平方向的偏离量
	竖直方向的偏移量
	晕染的距离
	颜色
```CSS
.box{
background-color: f9f9f9;
box-shadow: 5px 5px 5px grey;
}
```
# 3.文本处理
颜色：color
首行缩进：text-indent
字体大小：font-size
字体样式：font-family
文字粗细：font-weight
文字加粗：font-weight
文字水平居中：text-align
文字垂直居中：
	1. 设置所在容器的高度：height: 180px
	2. 设置行高与与之相同：line-height: 180px
文本阴影：text-shadow: 2px 2px 5px black;
	水平方向的便宜量
	数字方向的偏移量
	晕染的距离
	颜色
文本装饰：text-decoration
```CSS
.box p{
color: #666;
text-indent: 2em;
}
.box h1{
font-size: 50px;
font-family:'黑体';
font-weight: normal;
text-align: center;
height: 180px;
line-height: 180px;
text-shadow: 2px 2px 5px black;
text-decoration: dashed underline skyblue;
}
```
中文文字竖直显示：writing-mode
西文文字竖直显示：text-orientation
```CSS
.box span{
writing-mode: vertical-lr;
text-orientation: upright;
}
```
# 4.位置属性
浮动：有很多问题，现在一般不再使用
定位
绝对定位：position: absoulte
	绝对定位不会改变元素本身的位置属性
	在绝对定位下，所有位置属性（top、left等）默认以我们的页面作为参考（也即body）不以父容器作为参考进行定位
相对定位：position: relative
	相对定位不会改变元素本身的位置属性
	可以让内部的标签在定位是参考设置了相对定位属性的标签
可是区域定位：position: fixed

```CSS
.box span{
position: absolute;
top: 200px;
left: 5px;
}
```

```CSS
.box{
position: relative
}
```
# 5.Flex布局处理
```HTML
<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <title>Title</title>  
    <link rel="stylesheet" href="/static/web/css/text.css">  
</head>  
<body>  
  
<div class="flex-container">  
    <div class="flex-item">  
        <h1>1、CSS层叠样式表</h1>  
        <p>            层叠样式表是一种样式语言，用来描述HTML或XML文档的呈现。  
            CSS表述了在屏幕、纸质、音频等其他媒体上的元素应该如何被渲染的问题。  
            CSS是开放Web的核心语言之一，并根据W3C规范在Web浏览器中进行了标准化  
            以前，CSS规范的各个部分的开发是同步进行的，这种方式允许对最新的推荐的CSS版本  
            进行控制，你可能已经听说CSS1、CSS2、CSS3。  
            但是以后不会再有CSS4或者CSS5，相反，现在的一切都是没有版本号的CSS  
        </p>  
    </div>  
    <div class="flex-item">  
        <h1>1、CSS层叠样式表</h1>  
        <p>            层叠样式表是一种样式语言，用来描述HTML或XML文档的呈现。  
            CSS表述了在屏幕、纸质、音频等其他媒体上的元素应该如何被渲染的问题。  
            CSS是开放Web的核心语言之一，并根据W3C规范在Web浏览器中进行了标准化  
            以前，CSS规范的各个部分的开发是同步进行的，这种方式允许对最新的推荐的CSS版本  
            进行控制，你可能已经听说CSS1、CSS2、CSS3。  
            但是以后不会再有CSS4或者CSS5，相反，现在的一切都是没有版本号的CSS  
        </p>  
    </div>    <div class="flex-item">  
        <h1>1、CSS层叠样式表</h1>  
        <p>            层叠样式表是一种样式语言，用来描述HTML或XML文档的呈现。  
            CSS表述了在屏幕、纸质、音频等其他媒体上的元素应该如何被渲染的问题。  
            CSS是开放Web的核心语言之一，并根据W3C规范在Web浏览器中进行了标准化  
            以前，CSS规范的各个部分的开发是同步进行的，这种方式允许对最新的推荐的CSS版本  
            进行控制，你可能已经听说CSS1、CSS2、CSS3。  
            但是以后不会再有CSS4或者CSS5，相反，现在的一切都是没有版本号的CSS  
        </p>  
    </div>    <div class="flex-item">  
        <h1>1、CSS层叠样式表</h1>  
        <p>            层叠样式表是一种样式语言，用来描述HTML或XML文档的呈现。  
            CSS表述了在屏幕、纸质、音频等其他媒体上的元素应该如何被渲染的问题。  
            CSS是开放Web的核心语言之一，并根据W3C规范在Web浏览器中进行了标准化  
            以前，CSS规范的各个部分的开发是同步进行的，这种方式允许对最新的推荐的CSS版本  
            进行控制，你可能已经听说CSS1、CSS2、CSS3。  
            但是以后不会再有CSS4或者CSS5，相反，现在的一切都是没有版本号的CSS  
        </p>  
    </div></div>  
</body>  
</html>
```
1. 设置flex布局：display：flex
2. 最大宽度：max-width
3. 最小宽度：min-width
4. 
全局应用
```CSS
*{
margin: 0;
padding: 0;
}
```
最外层盒子flex-container
```CSS
.flex-container{
display: flex;
width: 100%;
max-width: 800px;
min-width: 500px;
margin: 0 auto;
background-color: red;
}
```
盒子中的元素flex-item
```CSS
.flex-item{
padding: 10px;
border: 1px solid #ccc;
background-color: #f9f9f9;
}
```
元素高度默认自适应，默认情况下flex-item会自动撑起flex-container的内容，红的的盒子背景并不会显示出来
更改flex-item的最大高度小于flex-container的高度，可以将背景显示出来

```CSS
.flex-item{
max-height: 500px
}
```
flex轴
竖直方向
	align-items: flex-start：元素置顶（默认属性）
	align-items: flex-end：元素置于尾部
	align-items: flex-content：元素居中
```CSS
.flex-container{
align-items: flex-start;
}
```
水平方向
元素在设置了flex布局后，如果没有给定指定的宽度，会默认横向撑开（给item宽度，也即应用了flex盒子内的元素）
justify-content: center：水平方向居中
justify-content: flex-start：水平方向左对齐
justify-content: flex-endl：水平方向右对齐
```CSS
.flex-item{
max-width: 200px;
}
```

```CSS
.flex-content{
justify-content: center;
}
```
	justify-content: center;
总结：
父级元素设置：display: flex
竖直方向：align-items
	flex-start：顶部
	flex-end：底部
	center：垂直居中
	水平方向：justify-content
	flex-start：左侧
	flex-end：右侧
	flex-center：水平居中

flex比例
给所有应用了.flex-item的元素这是flex: 1，表示每个元素的比例都是1:1:1:1
```CSS
.flex-item{
flex: 1
}
```
单独给特定的应用了flex-item的元素设置flex: 3，整体比例发生改变：1:3:1:1（以给第二个元素设置flex: 3为例）
```CSS
.flex-item nth-child(2){
flex: 3;
}
```
关于`:nth child(an+b)`
	是一个CSS伪类，首先找到所有当前元素的兄弟元素，然后按照位置先后顺序，从1开始排序，选择的结果为CSS伪类:nth-child括号中表达式(an+b)匹配到的元素集合(n=0,1,2,3...)
		- `0n+3`或者简单的`3`匹配第三个元素
		- `1n+0`或者简单的`n`匹配每个元素
		- `2n+0`或简单的`2n`匹配位置为2、4、6、8的元素
		- `2n+1`匹配位置为1、3、5、7的元素
		- `3n+4`匹配位置为4、7、13的元素
# grid布局