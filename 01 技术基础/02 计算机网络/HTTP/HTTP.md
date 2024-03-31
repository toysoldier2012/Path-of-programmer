#http

HyperText Transfer Protocol, un protocole de la couche application, permet de transmettre les données entre le client et le serveur, il a trois caractères principaux:

- Stateless. Bien que HTTP/1.1 apporte le cookies pour gérer l'état, le protocole lui-même est sans  état
- Extensible. HTTP permet de transmettre des objets variés, spécifiés par le champ d'entête Content-Type
- En modèle requête-réponse. Le modèle d'interaction définit une série de méthodes 

Ce protocole contient principalement deux partie: la requête et la réponse

# Requête

Une requête contient trois parties:

## 请求行

是HTTP请求的第一行，包含三个重要信息

- 请求方法
- 请求[[URI]]
- HTTP协议版本

一般格式如下

```bash
GET /index.html HTTP/1.1
```

常见的请求方法为GET，[[POST]]，PUT，DELETE，HEAD，OPTION，PATCH，CONNECT，TRACE

### 协议版本

HTTP/1.0，HTTP/1.1，HTTP/2

## Header

### 认证（Authentication）

`Authorization`头部可以包含必要的凭证信息，通常在使用基本认证（Basic Authentication）时，它会包含用户名和密码的组合，这些信息经过Base64编码后被包含在请求中。

### 内容类型（Content-Type）

这指明了发送给接收者的实体体（body）的媒体类型。

- `application/x-www-form-urlencoded`：用于提交HTML表单数据，每个键与其对应的值会被等号（`=`）连接，而键值对之间则由`&`符号分隔。
- `application/json`：以JSON格式发送，可以表示更复杂的数据结构，如对象、数组、数字、字符串等
- `multipart/form-data`：特别是在需要上传文件或发送包含文件和数据的复合消息时，会自动生成boundary字符串，用于分割数据
``` HTTP
--xyz123 
Content-Disposition: form-data; name="field1" 

value1 
--xyz123 
Content-Disposition: form-data; name="file"; filename="example.txt" Content-Type: text/plain
  
...文件内容... 
--xyz123--
```
- `text/plain`：简单文本数据，不进行任何编码
- `application/xml`：以XML格式发送数据
### 缓存控制（Cache-Control）

它用于指定缓存策略，控制数据被缓存的条件和时长，比如可以指定资源不被缓存。

### 用户代理（User-Agent）

包含了发起请求的客户端（如浏览器）的信息，服务器可以使用这些信息来确定如何最好地响应。

### 接受（Accept）

指明客户端愿意接收哪些类型的信息，比如`text/html`或`application/xml`。

## Body



# Réponse

Après avoir traité le requête du client par le serveur, le serveur renverra une réponse HTTP. La réponse contient 3 parties principaux: 

## Status codes

200+ les codes réussi
300+ redirect
400+ Client error
- 400 bad request
- 401 unauthorized
- 403 forbidden
- 404 not found
- 405 method not allowed
500+ Server error

![[Pasted image 20230926205129.png]]

# Réaliser

A voir [[Apache HTTP]]
