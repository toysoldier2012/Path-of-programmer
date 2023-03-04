
> [!question] 
> **Q: C'est quoi Mybatis** #D1 

# Hello Mybatis（通过Maven）

详见官网： https://mybatis.org/mybatis-3/zh/getting-started.html

![[Pasted image 20230304010809.png]]

## 1. 添加依赖

```xml
<dependency>  
  <groupId>org.mybatis</groupId>  
  <artifactId>mybatis</artifactId>  
  <version>3.5.6</version>  
</dependency>  
<dependency>  
  <groupId>mysql</groupId>  
  <artifactId>mysql-connector-java</artifactId>  
  <version>8.0.31</version>  
</dependency>
```

## 2. 构建SqlSessionFactory

```Java
String resource = {PATH_MYBATIS_CONFIG};
InputStream inputStream = Resources.getResourceAsStream(resource);
SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
```

## 3. 构建Mybatis XML配置文件

```Xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
  PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
  "https://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
  <environments default="development">
    <environment id="development">
      <transactionManager type="JDBC"/>
      <dataSource type="POOLED">
        <property name="driver" value="${driver}"/>
        <property name="url" value="${url}"/>
        <property name="username" value="${username}"/>
        <property name="password" value="${password}"/>
      </dataSource>
    </environment>
  </environments>
  <mappers>
	<mapper resource="mappers/UserMapper.xml"/>
  </mappers>
</configuration>
```

- environments：设置数据库环境，需要保持环境名唯一

- transactionManager
	- type:
		- JDBC：通过JDBC原生事务管理方式
		- MANAGED：通过其他方式管理，如Spring

- dataSource
	- type:
		- POOLED：使用数据库连接池
		- UNPOOLED：不使用数据库连接池
		- JNDI：表示使用上下文中的数据源

- properties：引入properties文件
	- resource

- typeAliases：指定特定类的别名
	- typeAlias
	- package：指定特定包下所有类的别名

- mappers
	- mapper
	- package：保证映射文件与接口的包名与本名一致

## 4. 创建Mapper映射文件

src/main/resources/mappers/UserMapper.xml

```xml
<?xml version="1.0" encoding="UTF-8" ?>  
<!DOCTYPE mapper  
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"  
        "https://mybatis.org/dtd/mybatis-3-mapper.dtd">  
<mapper namespace="com.xiaoyu.mapper.FilmMapper">  
    <select id="selectAllFilm" resultType="com.xiaoyu.pojo.Film">  
        select * from film  
    </select>  
</mapper>
```


## 5. 创建Mapper接口

src/main/java/com/xiaoyu/mybatis/mapper/UserMapper.java

```Java
public interface FilmMapper {  
   List<Film> selectAllFilm();  
}
```

## 6. 补齐代码

```Java
SqlSession sqlSession = sqlSessionFactory.openSession();  
FilmMapper mapper = sqlSession.getMapper(FilmMapper.class);  
List<Film> films = mapper.selectAllFilm();
```

