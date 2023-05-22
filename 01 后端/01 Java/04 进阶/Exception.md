#exception 

![[Pasted image 20230223222934.png]]

# 分类

## Runtime Exception

`ArithmeticException` (算术错误）
`ClassCastException` (类型转换错误）
`FileNotFoundException`
`IndexOutOfBoundsException`
`IllegalArgumentException` (参数错误比如方法入参类型错误)
`NullPointerException` (空指针错误)
`NumberFormatException` (字符串转换为数字格式错误，`IllegalArgumentException`的子类）
`SecurityException` (安全错误比如权限不够）
`UnsupportedOperationException` (不支持的操作错误比如重复创建同一用户)

*[原文链接](https://javaguide.cn/java/basis/java-basic-questions-03.html)*

## Checked Exception


## Error

`OutOfMemoryError`
`UnsupportedClassVersionError`

# Opération

- 抛出异常
	- `throw`

- 处理异常
	- `throws`
	- `try...catch...finally`
	- `try-with-resources` 

