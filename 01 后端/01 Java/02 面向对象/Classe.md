#class 

#todo 翻译

# Sections

1. Déclaration
	- en format CamelCase
	
2. Constructeur
	- en format CamelCase
	
3. [[Méthode]]
	- en format camelCase
	
4. block

# Classe spécifique

## 1. Classe abstract 
#abstract 

## 2. Interface 
#interface 

- L'interface est une abstraction d'un comportement spécifique.
- Les seules variables que l'on peut définir dans une interface sont des variables de la classe qui doivent être constantes 
- Toute classe qui implémente cette interface, doit au moins posséder les méthodes qui sont déclarées dans l'interface

- Java 9 之后，方法可以为 `private` 或者 `private static`

### La `default` méthode
#default

- Après Java 8, la méthode `default` permet de définir le comportement dans l'interface auquel elle est définie, elle évide de la redéfinir dans tous les classes d'implémentation 

- Il est possible de créer directement une instance d'une interface si tous les méthodes sont méthodes par défaut
- Une interface fille peut redéfinir la méthode par défaut sans le déclarer par défaut, dans ce cas elle redéfinir comme étant abstraite

- Dans la classe d'implémentation, on rappelle la méthode défaut dans l'interface par `Interface.super.method()

### L'interface locale

Elle ne capture que les variables statics du context englobant

### L'interface fonctionnelle

Elle a qu'une seule méthode abstraite

## 内部类 `

[Java内部类详解_weixin_30578677的博客-CSDN博客](https://blog.csdn.net/weixin_30578677/article/details/99659725?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1-99659725-blog-78625320.235%5Ev38%5Epc_relevant_sort&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1-99659725-blog-78625320.235%5Ev38%5Epc_relevant_sort&utm_relevant_index=2)

- 匿名内部类 #anonymousclass 

# Les Mots clés
#keyword

- [[Programmation orientée objet#^a41d5a|Les modificateurs d'accès]] 

- `static` #static 

Elle ne sont définies qu'une seule fois, quel que soit le nombre d'objet instanciés de la class
Non-static entity ne peut pas être utilisé dans static méthode

- `final` #final
	只能在构造器，初始化块，声明时赋值

- `instanceof` #instanceof 

- `this` #this 
	this est un instance d'un objet dans lequel il est utilisé
	
- super

- `synchronized` #synchronized
	Il permet de gérer l'accès concurrent aux variables et méthodes lors de traitements de [[Multi-thread]]

- `volatile` #volatile
	Il précise que la variable peut être changé par un périphérique ou de manière asynchrone  lors de traitements de [[Multi-thread]]
	
	共享变量
	在 Java 中，关键字 `volatile` 用于声明一个变量，表示该变量可能被多个线程修改。它确保变量的值始终从主内存中读取和写入，而不是缓存在线程的本地缓存中。这保证了一个线程对变量所做的更改立即对其他线程可见。
	当一个变量被声明为 `volatile` 时，会强制执行以下行为：
	1.  可见性：一个线程对 `volatile` 变量的更改立即对其他线程可见。当一个线程读取一个 `volatile` 变量时，它总是从主内存中读取最新的值。
	2.  原子性：对 `volatile` 变量的读取和写入是原子操作，意味着该变量的访问被视为一个单一、不可分割的操作。但是，涉及多个变量的复合操作并不是原子的，可能需要额外的同步机制。
	`volatile` 关键字在多个线程访问共享变量的场景中非常有用，它确保一个线程对变量的更改对其他线程立即可见。常见的应用场景包括标志位或状态指示器，需要一个线程对其进行更新，并被其他线程观察。
	需要注意的是，`volatile` 关键字并不能提供与锁或 `synchronized` 块相同级别的同步和线程安全性。它不适用于复杂的操作或维护多个变量之间的不变性。对于更复杂的并发场景，应使用其他同步机制，如锁或 `java.util.concurrent` 库中的类。

- `native` #native
	Une méthode native est une méthode implémenté dans une autre langage, il a la limite de la portabilité, mais avec une vitesse d'exécution plus rapide 

	使用 native 关键字说明这个方法是原生函数，也就是这个方法是用 C/C++语言实现的，并且被编译成了 DLL，由 java 去调用

# Comparaison

## `==`

- 对于基本数据类型来说，`==` 比较的是值。
- 对于引用数据类型来说，`==` 比较的是对象的内存地址。

## `equals()` 
#equals 

- **类没有重写 `equals()`方法** ：通过`equals()`比较该类的两个对象时，等价于通过`==`比较这两个对象，使用的默认是 `Object`类`equals()`方法。
- **类重写了 `equals()`方法** ：一般我们都重写 `equals()`方法来比较两个对象中的属性是否相等；若它们的属性相等，则返回 `true`(即，认为这两个对象相等)。
- String 重写了 `equals()` 方法

## `hashCode()`
#hashcode

``` Java
public native int hashCode();
```

相同的对象`hashCode`一定相同，反之不然，所以在将对象加入`hashSet`中时，先对比`hashCode`，如果一致，再调用`equals()` ，以确定对象是否真的一致

如果重写 `equals()` 时没有重写 `hashCode()` 方法的话就可能会导致 `equals` 方法判断是相等的两个对象，`hashCode` 值却不相等。