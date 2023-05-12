#string 

> [!question] 
> **Q: Les différences entre `String`, [[StringBuffer]], [[StringBuilder]]** #D1 
> - `String` 是不可变的
> - `StringBuffer` 对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全的。
> - `StringBuilder` 更快，线程不安全
> - 拼接字符最好不要用 `String + String` 或者  `"chaine1"&&"chaine2"`，过程中会创建 n 个 `StringBuilder`

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
String.intern()
```

## 删

```Java

```

## 改

```Java
toUpperCase()
toLowerCase()
```

## 查

```Java
compareTo()
// a value 0 if the argument string is equal to this string; 
// a value less than 0 if this string is lexicographically less than the string argument; 
// a value greater than 0 if this string is lexicographically greater than the string argument.
length()
charAt()
substring()
```

# 转换
^0e4978

- 与基本数据类型，包装类的转换
	- String --> 基本，`xxx.parceXxx()`
	- 基本 --> String，`String.valueOf()`

- 与char类型
	- `toCharArray()`
	- `String(char[])`

- 与byte类型
	- `getBytes()`
	- `String(byte[])`

# 特殊情况

``` Java
String ss1 = "abc";  
String ss2 = "abc 45";  
String ss3 = "abc 78";  
  
String[] ass1 = ss1.split(" ");  
String[] ass2 = ss2.split(" ");  
String[] ass3 = ss3.split(" ");

// 由于ss1 ss2 ss3是不同的字符串，ass1 ass2 ass3数组中的abc也引用不一样，不能用==对比
System.out.println(ass1[0] == ass2[0]);//false
```