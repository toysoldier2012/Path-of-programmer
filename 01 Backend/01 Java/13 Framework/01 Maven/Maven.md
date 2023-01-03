
# 安装以及Hello world

## 全手动方式配置

1. 下载

2. 配置conf/setting.xml

3. 配置环境变量

4. 创建项目

```shell
mvn archetype:generate
```

5. 配置POM文件

## Idea配置方式

### 安装Maven插件

1. Maven + Maven helper
2. 检查Maven设置

### 通过普通项目

1. 添加普通目录信息

![[Pasted image 20230101162525.png]]

2. 补全pom信息

```xml
<properties>  
  <maven.compiler.source>17</maven.compiler.source>  
  <maven.compiler.target>17</maven.compiler.target>  
  <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>  
</properties>

<packaging>war</packaging>

<plugins>  
  <plugin>
	<groupId>org.apache.maven.plugins</groupId>  
    <artifactId>maven-war-plugin</artifactId>  
    <version>3.2.2</version>  
  </plugin>
</plugins>
```

# [[核心概念]]



# [[单一架构案例]]


