---
title: "Ajax"
date: 2023-09-22T05:35:12-05:00
categories: ["Web"]
tags: ["request"]
---



# GET 还是 POST？
与 POST 相比，GET 更简单也更快，并且在大部分情况下都能用。

然而，在以下情况中，请使用 POST 请求：

- 不愿使用缓存文件（更新服务器上的文件或数据库）

- 向服务器发送大量数据（POST 没有数据量限制）

- 发送包含未知字符的用户输入时，POST 比 GET 更稳定也更可靠

***不刷新页面向服务器发送请求***

```javascript
const xhr = new XMLHttpRequest();
//设置方法和url
xhr.open('GET','http://127.0.0.1:8030/server?a=100')
xhr.send();
xhr.onreadystatechange = function(){
if(xhr.readyState == 4){  //0初始化。1open方法，2send方法，3部分返回结果，4全部结果
	if(xhr.status == 200){
         // console.log(xhr.status)
         // console.log(xhr.statusText)
         // console.log(xhr.getAllResponseHeaders())
         // console.log(xhr.response)
         demo.innerHTML = xhr.response
    }
  }
}
```

# 创建对象

```js
var xhr = new XMLHttpRequest();
```

# 向服务器发送请求

```js
xhr.open("GET","localhost:8000");
xhr.send()
```

# 异步 - True 或 False？
AJAX 指的是异步 `JavaScript` 和 `XML（Asynchronous JavaScript and XML）`。

`XMLHttpReques`t 对象如果要用于 AJAX 的话，其 `open()` 方法的 async 参数必须设置为 true：

异步：通过 AJAX，JavaScript 无需等待服务器的响应，而是：w
- 在等待服务器响应时执行其他脚本

- 当响应就绪后对响应进行处理

# `onreadystatechange` 事件
0. 请求未初始化
1. 服务器连接已建立
2. 请求已接收
3. 请求处理中
4. 请求已完成，且响应已就绪

# 请求`json`数据
在`open()`函数后面+
```js
xmlhttp.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
```
