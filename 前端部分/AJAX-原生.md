# AJAX-原生

## 1. 简介：

**AJAX 是一种在无需重新加载整个网页的情况下，能够更新部分网页的技术。**

**AJAX = 异步 JavaScript 和 XML**

本次课程主要结合JavaScript

## 2.XMLHttpRequest 

### 2.1XMLHttpRequest 对象

XMLHttpRequest是一种用于在Web浏览器中发送HTTP请求和接收响应的JavaScript API。它是AJAX的核心组件之一，允许开发人员通过JavaScript与服务器进行异步通信，而无需刷新整个页面。

通过XMLHttpRequest对象，可以指定请求的URL、请求方法、请求头、请求参数等。一旦发送请求，可以通过设置事件处理程序来监听请求的不同阶段，如请求已发送、请求已接收到响应等。同时，可以访问服务器返回的响应数据，并进行进一步的处理和操作。

XMLHttpRequest对象也支持异步请求，这意味着可以在发送请求后继续执行其他JavaScript代码，而不需要等待服务器的响应。一旦服务器返回响应，可以通过事件处理程序捕获响应，并在需要时更新页面内容或执行其他操作。

需要注意的是，尽管名字中包含"XML"，但XMLHttpRequest并不仅限于处理XML数据。它可以用于发送和接收各种类型的数据，例如JSON、HTML、纯文本等。

### 2.2创建 使用XMLHttpRequest 对象

1. 实例化XMLHttpRequest对象：
   ````js
   var xhr = new XMLHttpRequest();
   ```
   ````

2. 设置请求的方法和URL：
   ````js
   var method = 'GET'; // 请求方法，可以是GET、POST等
   var url = 'http://example.com/api'; // 请求的URL
   xhr.open(method, url, true); // 第三个参数指定是否异步，默认为true
   ```
   ````

3. 设置请求头部（可选）：
   ````js
   xhr.setRequestHeader('Content-Type', 'application/json'); // 设置请求的Content-Type
   xhr.setRequestHeader('X-Requested-With', 'XMLHttpRequest'); // 设置自定义请求头
   ```
   ````

4. 设置响应的回调函数：
   ````js
   xhr.onreadystatechange = function() {
     if (xhr.readyState === XMLHttpRequest.DONE) { // 请求完成
       if (xhr.status === 200) { // 响应状态码为200表示成功
         var response = xhr.responseText; // 响应内容
         // 在这里处理响应数据
       } else {
         // 处理请求错误
       }
     }
   };
   ```
   ````

5. 发送请求：
   ````js
   xhr.send();
   ```
   ````

案例：

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>AJAX请求示例</title>
</head>
<body>
  <h1>AJAX请求示例</h1>
  
  <button id="sendRequestBtn">发送请求</button>
  
  <script>
    document.getElementById('sendRequestBtn').addEventListener('click', function() {
      var xhr = new XMLHttpRequest();
      var method = 'POST';
      var url = 'http://example.com/api';
      xhr.open(method, url, true);
      xhr.setRequestHeader('Content-Type', 'application/json');
  
      xhr.onreadystatechange = function() {
        if (xhr.readyState === XMLHttpRequest.DONE) {
          if (xhr.status === 200) {
            var response = JSON.parse(xhr.responseText);
            // 在这里处理JSON格式的响应数据
            console.log(response);
          } else {
            // 处理请求错误
          }
        }
      };
  
      var data = {
        name: 'John',
        age: 25,
        email: 'john@example.com'
      };
  
      xhr.send(JSON.stringify(data));
    });
  </script>
</body>
</html>
```

## 3. POST与GET

GET请求：

- GET请求用于从服务器获取数据。它通过URL的查询参数将数据附加在请求的URL中，并将数据暴露在URL中，因此在浏览器的地址栏中可以看到。

- GET请求对数据长度有限制，因为URL的长度有限。一般来说，GET请求适合用于获取少量的非敏感数据。

- GET请求可被缓存，可以被收藏为书签，可以在浏览器历史记录中看到。

- GET请求的示例：

  ```js
  GET /api/users?id=123 HTTP/1.1
  Host: example.com
  ```

POST请求：

- POST请求用于向服务器提交数据。它将数据作为请求的正文发送，而不是作为URL的查询参数。因此，POST请求不会将数据暴露在URL中。

- POST请求没有数据长度限制，因为数据被包含在请求的正文中。

- POST请求不会被缓存，不会显示在浏览器的历史记录中。

- POST请求通常用于向服务器发送敏感数据、提交表单、上传文件等。

- POST请求的示例
  ```js
  POST /api/users HTTP/1.1
  Host: example.com
  Content-Type: application/json
  
  {"name": "John", "age": 25}
  ```

通常，GET请求用于获取数据，而POST请求用于提交或修改数据。在实际开发中，还可以使用其他HTTP请求方法，例如PUT和DELETE，以实现更复杂的数据操作。

## 4.JSON

JSON（JavaScript Object Notation）是一种轻量级的数据交换格式。它基于JavaScript的对象字面量语法，一种独立于编程语言的数据格式。

```json
{
  "name": "John",
  "age": 25,
  "isStudent": true,
  "address": {
    "street": "123 Main St",
    "city": "New York"
  },
  "hobbies": ["reading", "traveling", "cooking"]
}
```

在上述示例中，有一个包含多个键值对的JSON对象。它包括名为"name"、"age"、"isStudent"、"address"和"hobbies"的键。对应的值可以是字符串（如"name"），数值（如"age"），布尔值（如"isStudent"），对象（如"address"）或数组（如"hobbies"）。

在JavaScript中，可以使用`JSON.parse()`方法将JSON字符串解析为JavaScript对象，并使用`JSON.stringify()`方法将JavaScript对象序列化为JSON字符串。

```js
var jsonStr = '{"name": "John", "age": 25}';
var jsonObj = JSON.parse(jsonStr);
console.log(jsonObj.name); // 输出: John

var obj = { name: 'John', age: 25 };
var jsonString = JSON.stringify(obj);
console.log(jsonString); // 输出: {"name":"John","age":25}
```

