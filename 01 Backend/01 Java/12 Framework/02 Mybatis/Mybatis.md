
**Q: C'est quoi Mybatis** #D1 

# Hello Mybatis（通过Maven）

详见官网： https://mybatis.org/mybatis-3/zh/getting-started.html

1. 添加依赖

```xml
<dependency>  
  <groupId>org.mybatis</groupId>  
  <artifactId>mybatis</artifactId>  
  <version>3.5.11</version>  
</dependency>  
<dependency>  
  <groupId>mysql</groupId>  
  <artifactId>mysql-connector-java</artifactId>  
  <version>8.0.30</version>  
</dependency>
```

2. 构建SqlSessionFactory

```Java
String resource = {PATH_MYBATIS_CONFIG};
InputStream inputStream = Resources.getResourceAsStream(resource);
SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
```

3. 构建XML配置文件

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
    <mapper resource="org/mybatis/example/BlogMapper.xml"/>
  </mappers>
</configuration>
```

4. 创建Mapper映射文件

com/xiaoyu/mapper/FilmMapper.xml

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


5. 创建Mapper接口

com/xiaoyu/mapper/FilmMapper.java

```Java
public interface FilmMapper {  
   List<Film> selectAllFilm();  
}
```

6. 补齐代码

```Java
SqlSession sqlSession = sqlSessionFactory.openSession();  
FilmMapper mapper = sqlSession.getMapper(FilmMapper.class);  
List<Film> films = mapper.selectAllFilm();
```

