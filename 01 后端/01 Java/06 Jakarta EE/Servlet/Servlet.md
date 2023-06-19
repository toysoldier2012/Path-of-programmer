
> [!question] 
> **Q: C'est quoi Servlet** #D1 
> 
> Une norme de Java pour développer le web dynamique
> C'est une interface 

# Hello Servlet

1. New project -- maven-archetype-webapp
2. 修改pom.xml文件

```xml
<!--Complier error-->
<properties>  
	<maven.compiler.source>17</maven.compiler.source>  
	<maven.compiler.target>17</maven.compiler.target>  
	<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>  
</properties>

<dependencies>  
	<!--NoClassFoundError-->
	<dependency>
		<groupId>jakarta.servlet</groupId>  
		<artifactId>jakarta.servlet-api</artifactId>  
		<version>5.0.0</version>  
		<scope>provided</scope>  
	</dependency>
</dependencies>
  
```

3. 修改web.xml文件

```xml
<?xml version="1.0" encoding="UTF-8"?>  
<web-app version="4.0"  
         xmlns="http://xmlns.jcp.org/xml/ns/javaee"  
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd">  

<!--    XML配置方式-->
<!--    <servlet>-->  
<!--        <servlet-name>hello</servlet-name>&lt;!&ndash; 这里的name与下面的name一致即可 &ndash;&gt;-->
<!--        <servlet-class>com.xiaoyu.servlet.demo1.demo1</servlet-class>&lt;!&ndash; 使用到的class文件 &ndash;&gt;-->
<!--    </servlet>-->  
<!--    <servlet-mapping>-->  
<!--        <servlet-name>hello</servlet-name>&lt;!&ndash; 与上面的name一致 &ndash;&gt;-->
<!--        <url-pattern>/hello</url-pattern>&lt;!&ndash; 所映射的URL &ndash;&gt;-->  
<!--    </servlet-mapping>-->  
</web-app>
```

# 生命周期

1. 默认第一次被访问时，由容器创建

```java
@WebServlet(urlPatterns = "/demo", loadOnStartup = 1)
```

- loadOnStartup小于0，第一次被访问时创建，大于等于0，服务器启动时创建，数字越小优先级越高
- urlPatterns可以通过通配符匹配格式

2. 初始化

容器将调用```init()```方法，只执行一次

3. 请求处理

容器将调用```service()```方法

4. 终止服务

释放内存或关闭容器时，容器将调用```destroy()```方法

# 体系结构

Servlet --> GenericServlet --> HttpServlet

## HttpServlet

```java
doGet()
doPost()
```

## request

1. 获取请求行，请求头，请求体信息
2. 乱码问题
3. 转发

## response

1. 设置响应行，响应头，相应体
2. redirect

