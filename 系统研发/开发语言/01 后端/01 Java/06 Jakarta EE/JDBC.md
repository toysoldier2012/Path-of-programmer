#jdbc 

## 基本流程

1. 导入 java. Sql 包
2. 创建 Driver 对象
3. 创建 Connection 对象
4. 创建 PreparedStatement 对象
5. 执行 SQL 语句
6. 使用 ResultSet 对象
7. 关闭 ResultSet 对象
8. 关闭 PreparedStatement 对象
9. 关闭 Connection 对象
10. 结束

## 通用操作

- 增删改
- 查询
- Apache-DBUtils 包

## 什么情况下需要 Transaction

当一个完整的事务中有多个操作步骤时，需要多个步骤共进退，就要考虑通过事务解决，并且多个步骤要同时提交

## 会导致自动提交的步骤

- DDL 操作，一旦执行，就会自动提交，无法通过命令解决

- DML 操作，默认自动提交，需要设置 autocommit 属性

```Java
connection.setAutoCommit(false)
```

- 关闭连接会导致自动提交，只创建一个 connection

## 其他操作

- 手动提交/回滚数据

``` Java
connection.commit()
connection.rollback()
```

 - 在 close Connection 时，恢复自动提交
 
```Java
connection.setAutoCommit(true)
```

## 数据库连接池

- 必要性
- 第三方连接池

	- C 3 p 0
	- Druid
	- Dbcp
