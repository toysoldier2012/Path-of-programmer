# 后端

## [[Java]]

## 数据库

- 操作类型

	- DDL

	  Data Definition Language (DDL) statements are used to define the database structure or schema. Some examples:
	  
		- CREATE - to create objects in the database
		- ALTER - alters the structure of the database
		- DROP - delete objects from the database
		- TRUNCATE - remove all records from a table, including all - spaces allocated for the records are removed
		- COMMENT - add comments to the data dictionary
		- RENAME - rename an object

	- DML

	  Data Manipulation Language (DML) statements are used for managing data within schema objects. Some examples:
	  
		- SELECT - retrieve data from the a database
		- INSERT - insert data into a table
		- UPDATE - updates existing data within a table
		- DELETE - deletes all records from a table, the space for the records remain
		- MERGE - UPSERT operation (insert or update)
		- CALL - call a PL/SQL or Java subprogram
		- EXPLAIN PLAN - explain access path to data
		- LOCK TABLE - control concurrency

	- DCL

	  Data Control Language (DCL) statements. Some examples:
	  
		- GRANT - gives user’s access privileges to database
		- REVOKE - withdraw access privileges given with the GRANT command

	- TCL

	  Transaction Control (TCL) statements are used to manage the changes made by DML statements. It allows statements to be grouped together into logical transactions.
	  
		- COMMIT - save work done
		- SAVEPOINT - identify a point in a transaction to which you can later roll back
		- ROLLBACK - restore database to original since the last COMMIT
		- SET TRANSACTION - Change transaction options like isolation level and what rollback segment to use

- ORM编程思想

	- 一个表对应一个类
	- 一条记录对应一个对象
	- 一个字段对应一个属性

- 类型对照表


# 前端

### Html

### CSS

### Javascript

### Ajax

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

## 中间件

### HTTP

### Json

### XML

### Cookie

### session

### SSL/TLS

## 其他

### 工具

- Eclipse

	- 单元测试方法

- IDEA

	- 基本设置
	- 插件

### 操作系统

### 数据结构与算法

- 数据结构
- 算法

	- 经典算法

		- 二分法查找
		- 排序

			- 冒泡排序

### 项目管理

- Git
- Maven

	- 安装

		- 下载
		- 配置环境变量
		- 创建项目
		- 配置POM文件

	- 项目生命周期

		- clean

			- pre-clean
			- clean
			- post-clean

		- default

			- 

		- site

			- pre-site
			- site
			- post-site
			- deploy-site

	- 高级

		- 分模块思想

			- 拆分
désagrégation des projets
			- 聚合
Agrégation des projets
			- 继承
L'héritage du projet

				- 

			- 属性

				- 环境变量

			- 版本管理

## 附加知识

### Redis

### Tomcat

### Servlet

### Filter

### Listener

