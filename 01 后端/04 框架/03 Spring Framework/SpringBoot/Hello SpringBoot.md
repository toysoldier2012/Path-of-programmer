
# 基本步骤

~~1. 引入父包 (non néssensaire)~~

```xml
<parent>  
	<groupId>org.springframework.boot</groupId>  
	<artifactId>spring-boot-starter-parent</artifactId>  
	<version>3.1.0</version>  
</parent>
```

2. 引入依赖

```xml
<dependencies>  
	<dependency>  
		<groupId>org.springframework.boot</groupId>  
		<artifactId>spring-boot-starter-web</artifactId>  
	</dependency>  
</dependencies>
```

3. 引入插件

```xml
<build>  
	<plugins>  
		<plugin>  
			<groupId>org.springframework.boot</groupId>  
			<artifactId>spring-boot-maven-plugin</artifactId>  
		</plugin>  
	</plugins>  
</build>
```

4. 创建 main 程序

```java
package com.xiaoyu.springboot;  
  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  
  
@SpringBootApplication  
public class MainApplication {  
	public static void main(String[] args) {  
		SpringApplication.run(MainApplication.class, args);  
	}  
}
```

5. 创建 Mapping 文件

```java
package com.xiaoyu.springboot.controller;  
  
import org.springframework.web.bind.annotation.GetMapping;  
import org.springframework.web.bind.annotation.RestController;  
  
@RestController  
public class HelloController {  
	@GetMapping("/hello")  
	public String hello(){  
		return "Hello, Spring Boot 3";  
	}  
}
```

Ou

Créer un projet par Spring Initializr

# 基本特性

## 1. 简化整合

整合了依赖包，服务器

## 2. 简化配置

集中管理配置文件
`reasources/application.properties`
配置基本都有默认值
[[properties]]

## 3. 简化开发

## 4. 简化部署

## 5. 简化运维

jar 包同目录下创建一个配置文件即可修改配置参数