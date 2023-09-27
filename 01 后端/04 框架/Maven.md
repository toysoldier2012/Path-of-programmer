
# Hello Maven

## 1. 全手动方式配置

1. 下载
2. 配置conf/setting.xml
3. 配置环境变量
4. 创建项目

```shell
mvn archetype:generate
```

5. 配置POM文件

## 2. Idea配置方式

### 安装Maven插件

1. Maven + Maven helper
2. 检查Maven设置

### 通过普通项目

1. 添加普通目录信息

![[Pasted image 20230101162525.png]]

2. 补全pom信息

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">  
  <modelVersion>4.0.0</modelVersion>  
  
  <groupId>org.xiaoyu</groupId>  
  <artifactId>JavawebGettingStart</artifactId>  
  
  <!--打包方式-->
  <packaging>war</packaging>  
  <version>1.0-SNAPSHOT</version>  

<!--Java版本错误-->
  <properties>
	<maven.compiler.source>17</maven.compiler.source>  
    <maven.compiler.target>17</maven.compiler.target>  
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>  
  </properties>
  
  <name>JavawebGettingStart Maven Webapp</name>  
  <url>http://maven.apache.org</url>  
  
  <dependencies>
	<dependency>
		<groupId>junit</groupId>  
		<artifactId>junit</artifactId>  
	    <version>4.13.2</version>  
	    <scope>test</scope>  
    </dependency>
  </dependencies>  
  <build>
    <finalName>JavawebGettingStart</finalName>  
    <plugins>
      <!--打包插件-->
      <plugin>
		<groupId>org.apache.maven.plugins</groupId>  
        <artifactId>maven-war-plugin</artifactId>  
        <version>3.2.2</version>  
      </plugin>
    </plugins>
  </build>
</project>
```

# [[核心概念]]
## POM
#pom 

Project Object Model，项目对象模型

## 项目生命周期

- Clean
	- Pre-clean
	- Clean
	- Post-clean
- Site
	- Pre-site
	- Site
	- Post-site
	- Deploy-site	
- Default
	- Validate
	- Generate-sources
	- Process-sources
	- Generate-resources
	- Process-resources
	- Compile
	- Generate-test-sources
	- Process-test-sources
	- Generate-test-resources
	- Process-test-resources
	- Test-compile
	- Process-test-classes
	- Test
	- Prepare-package
	- Package
	- Pre-integration-test
	- Integration-test
	- Verify
	- Install
	- Deploy

## 聚合工程
#todo 

# [[单一架构案例]]
