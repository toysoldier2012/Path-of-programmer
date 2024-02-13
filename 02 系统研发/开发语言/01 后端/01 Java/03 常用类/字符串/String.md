#string

# 特点

- String est immutable, mais partagé entre les threads 
- La littérale de `String` est partagé, mais pas les strings obtenu par `+` et `substring`

# 常用方法

## 增

```Java
String.intern()
```

## 查

```Java
compareTo()
// a value 0 if the argument string is equal to this string; 
// a value less than 0 if this string is lexicographically less than the string argument; 
// a value greater than 0 if this string is lexicographically greater than the string argument.

length()

isEmpty()
isBlank()

equals()
equalsIgnoreCase()

startWith()
endWith()

indexOf()
lastIndexOf()
```

## [[Conversion#^syNSg3FJ||Conversion]]

```Java
toUpperCase()
toLowerCase()

substring()
charAt()
replace()
strip()

join()
repeat()
```

### Conversion entre les types primitives

`Xxxx.parseXxxx` n'existe pas dans `Character`
Avec un opération `+`, tous les autres types des opérantes vont convenir en `String`
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
