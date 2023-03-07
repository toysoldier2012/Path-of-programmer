
详见官网： https://mybatis.org/mybatis-3/zh/getting-started.html

![[Pasted image 20230304205719.png]]

# 添加依赖

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

# 构建Mybatis XML配置文件

```Xml
<?xml version="1.0" encoding="UTF-8" ?>  
<!DOCTYPE configuration  
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"  
        "https://mybatis.org/dtd/mybatis-3-config.dtd">  
<configuration>  
    <properties resource="jdbc.properties"/>  
  
    <typeAliases>
	    <!--<typeAlias type="com.xiaoyu.mybatis.pojo.User"></typeAlias>-->  
        <package name="com.xiaoyu.mybatis.pojo"/>  
    </typeAliases>  
    <environments default="development">  
        <environment id="development">  
            <transactionManager type="JDBC"/>  
            <dataSource type="POOLED">  
                <property name="driver" value="${jdbc.driver}"/>  
                <property name="url" value="${jdbc.url}"/>  
                <property name="username" value="${jdbc.username}"/>  
                <property name="password" value="${jdbc.password}"/>  
            </dataSource>
        </environment>
    </environments>
    <mappers>
	    <!--<mapper resource="mappers/UserMapper.xml"/>-->  
        <package name="com.xiaoyu.mybatis.mapper"/>  
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

# 创建jdbc.properties文件

``` properties
jdbc.driver=com.mysql.cj.jdbc.Driver  
jdbc.url=jdbc:mysql://localhost:3306/ssm?serverTimezone=UTC  
jdbc.username=root  
jdbc.password=evvf8YXEEB
```

# 创建Mapper接口

^757291

src/main/java/com/xiaoyu/mybatis/mapper/UserMapper.java

```Java
package com.xiaoyu.mybatis.mapper;  
  
import com.xiaoyu.mybatis.pojo.User;  
  
import java.util.HashMap;  
import java.util.List;  
  
public interface UserMapper {  
   List<User> selectUsers();  
}
```

# 创建Mapper映射文件

src/main/resources/mappers/UserMapper.xml

```xml
<?xml version="1.0" encoding="UTF-8" ?>  
<!DOCTYPE mapper  
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"  
        "https://mybatis.org/dtd/mybatis-3-mapper.dtd">  
  
<mapper namespace="com.xiaoyu.mybatis.mapper.UserMapper">  
<!--    List<User> selectUsers();-->  
    <select id="selectUsers" resultType="user">  
        select * from t_user;  
    </select>  
</mapper>
```

# 补齐代码

```Java
String resource = {PATH_MYBATIS_CONFIG};
InputStream inputStream = Resources.getResourceAsStream(resource);
SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
SqlSession sqlSession = sqlSessionFactory.openSession();  
FilmMapper mapper = sqlSession.getMapper(FilmMapper.class);  
List<Film> films = mapper.selectAllFilm();
```
