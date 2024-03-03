#http #entity #httpentity 

Pour construire le body d'une requête [[POST]]

# Les types différents

## `UrlEncodedFormEntity`

 Pour construire un `application/x-www-form-urlencoded` entity

```java
// 添加表单参数
List<NameValuePair> urlParameters = new ArrayList<>();
urlParameters.add(new BasicNameValuePair("param1", "value1"));
urlParameters.add(new BasicNameValuePair("param2", "value2"));
post.setEntity(new UrlEncodedFormEntity(urlParameters));
```

`NameValuePair` est un interface de [[Apache HTTP]], pour construire le key-value pair entity, une classe commune est `BasicNameValuePair`

Si on a une [[List]] dans l'entity, insérer la list des values avec le même key

```java
// 假设我们要发送一个名为"items"的数组 
urlParameters.add(new BasicNameValuePair("items", "item1")); 
urlParameters.add(new BasicNameValuePair("items", "item2")); 
urlParameters.add(new BasicNameValuePair("items", "item3"));
```

## `StringEntity`

Construit un `application/json` entity

```java 
StringEntity entity = new StringEntity(json);
```

## `MultipartEntityBuilder`

Pour construire un `multipart/form-data` entity

```java
// 使用MultipartEntityBuilder构建multipart/form-data请求体
MultipartEntityBuilder builder = MultipartEntityBuilder.create();

// 添加文本字段
builder.addTextBody("field1", "value1", ContentType.TEXT_PLAIN);
// 添加文件
builder.addBinaryBody("file", new File("/path/to/file"), ContentType.APPLICATION_OCTET_STREAM, "filename");

// 生成请求实体
HttpEntity entity = builder.build();
```

# EntityUtils

`.toString()`

```java
String entityContent = EntityUtils.toString(entity, StandardCharsets.UTF_8);
```

