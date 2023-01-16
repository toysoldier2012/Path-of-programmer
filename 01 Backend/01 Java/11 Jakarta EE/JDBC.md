
# 基本流程

1. 导入java.sql包
2. 创建Driver对象
3. 创建Connection对象
4. 创建PreparedStatement对象
5. 执行SQL语句
6. 使用ResultSet对象
7. 关闭ResultSet对象
8. 关闭PreparedStatement对象
9. 关闭Connection对象
10. 结束

***

# 通用操作

- 增删改
- 查询
- Apache-DBUtils包

***

## 什么情况下需要Transaction

当一个完整的事务中有多个操作步骤时，需要多个步骤共进退，就要考虑通过事务解决，并且多个步骤要同时提交

***

## 会导致自动提交的步骤

- DDL操作，一旦执行，就会自动提交，无法通过命令解决

- DML操作，默认自动提交，需要设置autocommit属性

```Java
connection.setAutoCommit(false)
```

- 关闭连接会导致自动提交，只创建一个connection

***

## 其他操作

- 手动提交/回滚数据

``` Java
connection.commit()
connection.rollback()
```

 - 在close Connection时，恢复自动提交
 
```Java
connection.setAutoCommit(true)
```

***

## 数据库连接池

- 必要性
- 第三方连接池

	- c3p0
	- druid
	- dbcp
