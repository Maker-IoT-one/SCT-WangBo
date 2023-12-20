# jQuery-Ajax

ajax是一种异步无刷新的技术

# 1.$.ajax

jQuery调用Ajax方法：

```
格式：$.ajax({});
	参数：
		type：请求方式GET/POST
		url：请求地址url
		async：是否异步，默认true表示异步
		data：发送到服务器的数据
		dataType：预期服务器返回的数据类型
		contentType：设置请求头
		success：请求成功时调用次函数
		error：请求失时调用此函数
```

get请求

