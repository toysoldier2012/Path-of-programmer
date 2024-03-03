
Web 容器
	封装 Http 协议，简化操作
Servlet 容器
	支持 Servlet/JSP 规范

# 基本操作

- 下载，安装，乱码解决，开启，关闭
- 配置 pom

```xml
<plugin>  
	<groupId>org.apache.tomcat.maven</groupId>  
	<artifactId>tomcat7-maven-plugin</artifactId>  
	<version>2.2</version>  
	<!--<port></port>-->  
	<!--<path></path>-->  
</plugin>
```
