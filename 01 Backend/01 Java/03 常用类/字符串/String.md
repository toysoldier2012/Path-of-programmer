
# 特点

- 类特性
	- 不可被继承
	- Comparable接口
	- Serializable接口

- 对象特性
	- 不可变

# 常用方法

## 增

```Java

```

## 删

```Java

```

## 改

```Java

```

## 查

```Java
compareTo()
// a value 0 if the argument string is equal to this string; 
// a value less than 0 if this string is lexicographically less than the string argument; 
// a value greater than 0 if this string is lexicographically greater than the string argument.
length()
```

# 转换

- 与基本数据类型，包装类的转换
	- String --> 基本，xxx.parceXxx()
	- 基本 --> String，String.valueOf()

- 与char类型
	- toCharArray()
	- String(char[])

- 与byte类型
	- getBytes()
	- String(byte[])

**Q: Les différences entre String, StringBuffer, StringBuilder** #D1 

1. String n'est 