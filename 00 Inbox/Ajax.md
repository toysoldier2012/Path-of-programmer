
- 用途
- 依赖

	- NodeJS
	- express
	- JQuery

		- GET/POST发送
		- ajax发送

	- axios

- 基本模板

	- HTML页面

		- const xhr = new XMLHttpRequest();
xhr.open('POST', 'http://127.0.0.1:8000/all-server');
xhr.setRequestHeader('content-type', 'application/x-www-form-urlencoded');
xhr.setRequestHeader('abc', 'cba');
xhr.send('a=100&b=200');

xhr.onreadystatechange = function(){
    if (xhr.readyState === 4) {
        if (xhr.status >= 200 && xhr.readyState < 300) {
            console.log(xhr);
            result.innerHTML = xhr.response;
        } else {
            
        }
    }
}

	- Js页面

		- const express = require("express");

const app = express();

app.get('/server', (request, response)=>{
    response.setHeader('Access-Control-Allow-Origin', '*');
    response.send('Hello Ajax');
});

app.listen(8000, ()=>{
    console.log('listening...');
});

- 常见操作

	- GET
	- POST
	- 对JSON的操作
	- 延迟响应
	- 取消发送请求
	- 重复发送请求