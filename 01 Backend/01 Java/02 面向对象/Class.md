
# Entité

1. Déclaration

2. Constructeur

3. [[Method]]

4. block



# 特殊类


- [[Interface]]
- 内部类



# Objet

- 匿名对象

# == 和 `equals()` 的区别

## ==

-   对于基本数据类型来说，`==` 比较的是值。
-   对于引用数据类型来说，`==` 比较的是对象的内存地址。

## `equals()` 

-   **类没有重写 `equals()`方法** ：通过`equals()`比较该类的两个对象时，等价于通过`==`比较这两个对象，使用的默认是 `Object`类`equals()`方法。
-   **类重写了 `equals()`方法** ：一般我们都重写 `equals()`方法来比较两个对象中的属性是否相等；若它们的属性相等，则返回 `true`(即，认为这两个对象相等)。

String重写了`equals()`方法

## `hashCode()`

``` Java
public native int hashCode();
```

相同的对象`hashCode`一定相同，反之不然，所以在将对象加入`hashSet`中时，先对比`hashCode`，如果一致，再调用`equals()` ，以确定对象是否真的一致

如果重写 `equals()` 时没有重写 `hashCode()` 方法的话就可能会导致 `equals` 方法判断是相等的两个对象，`hashCode` 值却不相等。

# Mot clé

- [[Programmation orientée objet#^683229|Règles de visibilité]]
- static
- final
- abstract
- native
	使用native关键字说明这个方法是原生函数，也就是这个方法是用C/C++语言实现的，并且被编译成了DLL，由java去调用


- this

- synchronized
- volatile

- transient
- native

