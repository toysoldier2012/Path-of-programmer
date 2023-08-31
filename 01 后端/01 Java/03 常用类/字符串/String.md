#string

# 特点

- 类特性
	- 不可被继承
	- Comparable 接口
	- Serializable 接口

- 对象特性
	- 不可变

- String 重写了 `equals()` 方法，用于对比 String 的内容

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

## [[Conversion#^syNSg3FJ||Conversion]]

### Type primitif

`Xxxx.parseXxxx` n'existe pas dans `Character`
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
