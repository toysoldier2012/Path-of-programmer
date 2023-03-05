
# 类型对照表

![[Pasted image 20230104152938.png]]

# [[Transaction]]

# 隔离级别

READ UNCOMMITTED，允许读取**未提交数据** ^905ad9

READ COMMITTED，只允许读取其他事务**已提交的数据** ^7702a8

REPEATABLE READ，在T1事务持续期间，禁止其他事务对**此字段的操作** ^6e5ab9

SERIALIZABLE，在某事务读取一个表中的字段时，禁止其他事务对**该表的操作** ^2051ad