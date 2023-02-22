
> [!question] 
> **Q: A quoi sert Tomcat** #D1 

Web容器
	封装Http协议，简化操作
Servlet容器
	支持Servlet/JSP规范

# 基本操作

- 下载，安装，乱码解决，开启，关闭
- 配置pom

```xml
<plugin>  
	<groupId>org.apache.tomcat.maven</groupId>  
	<artifactId>tomcat7-maven-plugin</artifactId>  
	<version>2.2</version>  
	<!--<port></port>-->  
	<!--<path></path>-->  
</plugin>
```
