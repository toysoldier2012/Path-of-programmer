#http

HyperText Transfer Protocol, un protocole de la couche application, permet de transmettre les données entre le client et le serveur, il a trois caractères principaux:

- Stateless. Bien que HTTP/1.1 apporte le cookies pour gérer l'état, le protocole lui-même est sans  état
- Extensible. HTTP permet de transmettre des objets variés, spécifiés par le champ d'entête Content-Type
- En modèle requête-réponse. Le modèle d'interaction définit une série de méthodes 

# Version de HTTP

## HTTP/1.0

## HTTP/1.1

## HTTP/2

Ce protocole contient principalement deux partie: la requête et la réponse

# 请求

请求包含请求行，请求头，请求体三个部分组成

## 请求行

是HTTP请求的第一行，包含三个重要信息

- 请求方法
- 请求[[URI]]
- HTTP协议版本

一般格式如下

```bash
GET /index.html HTTP/1.1
```

常见的请求方法为GET，POST，PUT，DELETE，HEAD，OPTION，PATCH，CONNECT，TRACE

### 协议版本

HTTP/1.0，HTTP/1.1，HTTP/2

## Header



## Body



# 响应

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