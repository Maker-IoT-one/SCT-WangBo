## JavaScript

### 获取标签
 通过标签id获取标签：
 `doucument.getElementById`
```js
var block = document.getElementById('id')
console.log(block)
```
通过console.log打印内容
`consele.log`
```js
console.log(blok)
```
通过textcontent属性改变文本内容
`block.textContent`
```js
block.textContent = 'JS设置的文本'
```
通过标签名称获取多个标签内容
```js
var contents = document.getElementsByTagName('p')
console.log(contents)
```
	此时contents是一个伪数组（假设共计有4个p标签）
	写死的数据
```js
contents[0].textContent = '第一个p标签'
for(var i = 0; i<content.length;i++){
	contents[i].textContent = '新的内容'
}
```
根据返回的数组进行渲染的数据
```js
var contents = doucment.getElementsByTagName('p')
console.log(contents)
var textArr = [
'镇山的虎',
'敏捷的豹',
'远见的鹰',
'善战的狼'
]
for (var i = 0; i < contents.length; i++){
	contents[i].textContent = textArr[i]
}
```
但是上述的方法都比较死板，在HTML5中提供以下方法
`doucment.querySelectrAll`
1. 通过标签名获取标签
`document.querySelectorAll('p')`
2. 通过类名获取标签
`document.querySelectorAll('.text')`
3. 通过父标签的id获取标签
`document.querySelectorAll('#container p')`

```js
var contents = document.querySelectorAll('p')
console.log(contents)
var textArr = [
'镇山的虎',
'敏捷的豹',
'远见的鹰',
'善战的狼'
]
for (var i = 0; i < contents.length; i++){
	contents[i].textContent = textArr[i]
}
```

获取单个（选择器匹配到的第一个元素）
`document.querySlector('')`
```js
document.querySelector('.item')
```
获取相邻的标签
获取前一个同级标签`previousElementSibling`
获取后一个同级标签`nextElementSibling
```js
var secondItem = document.querySelector('.item')
secondItem.previousElementSibling.textContent = '划水的鱼'
secondItem.nextElementSibling.textContent = '装饭的桶'
```
获取父元素`parentNode`
```js
var secondItem = document.querySelector('.item')
secondItem.previousElementSibling.textContent = '划水的鱼'
secondItem.nextElementSibling.textContent = '装饭的桶'

var container = secondItem.parentNode
console.log(container)
container.textContent = '新内容'
```
获取内部元素`children`
```js
var items = conatiner.children
console.log(items)
```
### 样式处理
```html
<div id='block'>默认内容</div>
```
```css
div{
width: 100px;
height: 100px;
border: 1px dashed #ccc;
margin-bottom: 10px;
}
.changeStyle{
width = '80px';
height = '80px';
background-color = 'tomato';
}
```
通过id获取标签改变样式
```js
var block = document.querySelectory('#block')
block.className = 'changeStyle'
```
### 文本处理
普通文本处理`textContent`属性
有生成需求`innerHTML`
```css
.bold-text{
font-size: 30px;
font-weight: 700;
}
```

```js
block.innerHTML = '普通内容<span class="bold-text">加粗的文本</span>'
```
### 事件处理

一些常见的事件
1. `click`：当用户点击元素时触发事件。
    
2. `mouseover`：当鼠标移入元素时触发事件。
    
3. `mouseout`：当鼠标移出元素时触发事件。
    
4. `keydown`：当按下键盘按键时触发事件。
    
5. `keyup`：当释放键盘按键时触发事件。
    
6. `submit`：当表单提交时触发事件。
    
7. `focus`：当元素获得焦点时触发事件。
    
8. `blur`：当元素失去焦点时触发事件。
    
9. `change`：当表单元素的值改变时触发事件。
    
10. `scroll`：当元素滚动时触发事件。

传统的方法
```js
block.onclick = function(){
alert('surprise!')
}
block.onclick = function(){
alert('surprise again!')
}
```
	问题：会发生覆盖，第一次的alert并不会生效
使用`addEventListener`避免覆盖
```js
block.addEventListener('click', function(){
alert('surprinse')

block.addEventListener('click', function(){
alert('surprinse')
})
```
### 定时器
延迟定时器
setTimeout
```js
setTimeout(function(){
alert('surprise')
},2000)
```
间隔计时器
```js
setInterval(function(){
alert('surprise')
},2000)
```

### ES6
变量和常量
var--->let
块与作用域
在作用域声明的let变量，在其他作用域无法使用
下面这种方式会报错：count is not defind
```js
{
let count = 0
count++
}
console.log(count)
```
常量：不能修改的容器
```js
{
let count = 0
count++
const BASE_URL = 'http://web.wangbo.com/api'
}
```
模板字符串
通过单引号、双引号反引号书写字符串
反引号添加变量可以换行，使用${}
```js
const str1 = 'abc'
const strdouble = 'abc'
const str2 = `efg${str1}
这也是字符串的内容（反单引号，本行换行）
`

```

解构赋值
```js
{
	const arr[a,b,c] = [1,2,3]
	console.log(a,b,c)

	const obj = {
	username: '王博',
	age: 18,
	gender: 'male'
	}
	console.log(username,userAge)

	const {username, age: userAge, ...otherInfo} = {
	username: '王博',
	age: 18,
	gender: 'male',
	category: 'user'
	}
	console.log(username,userAge,otherInfo)
}
```

数组和对象的扩展
```js
const arr1 = [1,2,3]
const arr2 = [4,5,6]
const arr3 = [...arr1,...arr2]
console.log(arr3)


const obj1 = {
	a:1
}

const obj2 = {
	b:2
}
const obj3 = {
	naem: '王博',
	...obj1,
	...obj2
}

```

数组方法

类

```js
class A{
	consture(name,age){
	this.name = name
	this.age = age
	}
	intruduce(){
		console,log(`我的名字是${this.name},我的年龄是${this.age}`)
	}
}

const a1 = nwe A('王博', 18)
console.log(a1)
a1.intruduce()

class B extends A{
	s = constructor(name,age,gender)
	super(anme,age)
	this.gender = gender
	sayHello(){
		console.log('你好我是' + this.name)	
	}
}

const b1 = new B('小张', 18, 男)
console.log(b1)
b1.sayHelllo()
b1.intruduce()
```

箭头函数
```js
const getSum1 = function(n){
	return n + 3
}

const getSum1 = n => n+3
console.log(getSum1(10))

const getSum2 = (n1,n2) = n1 + n2
console.lgo(getSum2(10,20))

const getSum3 = (n1,n2,...other) => console.log(n1,n2,other)
console.log(getSume3(10,20,200,300))

const gerResult = arr => {
	const sum = 0
	arr.forEach(item => sum+=item)
	return sum
}
console.log(getResoult([1,2,3,4,5]))
```

```js
// 使用普通函数计算数组中每个元素的平方
function squareElements(arr) {
  var result = [];
  
  for (var i = 0; i < arr.length; i++) {
    result.push(arr[i] * arr[i]);
  }
  
  return result;
}

var numbers = [1, 2, 3, 4, 5];
var squared = squareElements(numbers);

console.log(squared); // 输出 [1, 4, 9, 16, 25]

// 使用箭头函数计算数组中每个元素的平方
const squareElements = (arr) => {
  let result = [];
  
  for (let i = 0; i < arr.length; i++) {
    result.push(arr[i] * arr[i]);
  }
  
  return result;
}

const numbers = [1, 2, 3, 4, 5];
const squared = squareElements(numbers);

console.log(squared); // 输出 [1, 4, 9, 16, 25]

```

promie 异步处理

同步和异步
同步：
	函数按照顺序执行
	可能发生阻塞
	常见异步：
		定时器
		Ajax
异步：
	异步任务被创建后，会创建一个任务队列进行等待，等待以后通过一定的机制，再添加到我们的主线程中进行执行
事件循环

异步任务的执行时在当前已经触发了同步任务而触发的

```js
console.log('任务1：......同步')
console.log('任务2：......同步')

setTimeout(() =>{
	console.log('任务4：...异步')
},1000)

console.log('任务3：......同步')
```
输出结果为：
	1
	2
	3
	4
并非
	1,2,4,3