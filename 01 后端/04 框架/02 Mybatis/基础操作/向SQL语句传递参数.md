
# 单参数

``` xml
<!--    User selectUserById(int id);-->  
<select id="selectUserById" resultType="User">  
	select * from t_user where id = #{id};  
</select>
```

#{}：占位符拼接
${}：字符串拼接，需要加 ' '

# 多参数

## ~~1. 通过多个参数~~

``` xml
<!--    User checkLogin(String username, String password);-->  
<select id="checkLogin" resultType="User">  
	select * from t_user where username = #{arg0} and password = #{arg1}  
</select>
```

或者param1, param2

## ~~2. 通过Map~~

``` xml
<!--    User checkLoginByMap(Map<String, Object> map);-->  
<select id="checkLoginByMap" resultType="User">  
	select * from t_user where username = #{username} and password = #{password}  
</select>
```

``` java
Map<String, Object> userMap = new HashMap<>();  
userMap.put("username", "admin3");  
userMap.put("password", "123456");  
  
User admin3 = mapper.checkLoginByMap(userMap);
```

## 3. 通过注解

``` xml
<!--    Boolean checkLoginByParam(@Param("username") String username, @Param("password") String password);-->  
<select id="checkLoginByParam" resultType="Boolean">  
	select * from t_user where username = #{username} and password = #{password}  
</select>
```

或者param1, param2

## 4. 通过Class

``` xml
<!--    void insertUser(User user);-->  
<insert id="insertUserByUser">  
	insert into t_user values(#{id}, #{username}, #{password}, #{age}, #{gender}, #{email});  
</insert>
```

# 模糊查询`LIKE`

1. 通过`'%${}%'`拼接
2. 通过`concat('%', #{}, '%')`拼接
3. 通过`"%"#{}"%"`拼接

``` xml
<!--    List<Map<String, Object>> getUsersByName(String userName);-->  
<select id="getUsersByName" resultType="Map">  
    <!--        select * from t_user where username like '%${username}%'-->  
	<!--        select * from t_user where username like concat('%', #{username}, '%')-->
	select * from t_user where username like "%"#{username}"%"  
</select>
```

# 批量查询`IN`

1. 通过${}，字符串拼接实现

# 表名/字段名

1. 通过${}，字符串拼接实现

