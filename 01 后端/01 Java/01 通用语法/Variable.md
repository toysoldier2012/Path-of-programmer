#variable 

# 类型

## 1. Type élémentaire
#primitivedatatype

1.  `byte`：1字节（8位），范围：-128 到 127
2.  `short`：2字节（16位）， 范围：-32,768 到 32,767
3.  `int`：4字节（32位）， 范围：-2,147,483,648 到 2,147,483,647
4.  `long`：8字节（64位），范围：-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807
5.  `float`：4字节（32位），范围：IEEE 754单精度浮点数格式，可表示大约 ±1.4 x 10^-45 到 ±3.4 x 10^38 的值
6.  `double`：8字节（64位）， 范围：IEEE 754双精度浮点数格式，可表示大约 ±4.9 x 10^-324 到 ±1.8 x 10^308 的值
7.  `char`：2字节（16位），范围：Unicode 字符（0 到 65,535）
8.  `boolean`：不定，通常被映射为1字节，可以表示 `true` 或 `false` 值

请注意，这些长度是Java规范中定义的标准长度，但具体的实现可能会有所不同。此外，还有其他与平台相关的整数类型（如`char`的无符号版本`char`）和大数字类型（如`BigInteger`和`BigDecimal`），它们的长度可以根据具体的库和需求而变化。

## 2. [[String]]

## 3. 引用类型

### 引用类别

#### 强引用

1. 平时创建的引用类型皆为强引用
2. 回收方式：当没有任何引用指向对象时，Garbage Collected（System.gc）会调用finalize方法

#### 软引用

1. 通过SoftReference类包装

```Java
SoftReference<byte[]> softReference = new SoftReference<>(new byte[1024 * 1024 * 10]);
softReference.get();
```

2. 空间不够时，会被自动回收
3. 可以用于缓存

#### 弱引用

1. 通过WeakReference类包装

```java
WeakReference<Person> personWeakReference = new WeakReference<>(new Person());  
System.gc();
```

2. 被垃圾回收器发现时，直接回收
3. ThreadLocal

#### 虚引用

1. 通过PhantomReference包装
2. 无法获取被包装对象
3. 堆外内存

### 拷贝类型

- **浅拷贝**：浅拷贝会在堆上创建一个新的对象（区别于引用拷贝的一点），不过，如果原对象内部的属性是引用类型的话，浅拷贝会直接复制内部对象的引用地址，也就是说拷贝对象和原对象共用同一个内部对象。
- **深拷贝** ：深拷贝会完全复制整个对象，包括这个对象所包含的内部对象。
- **引用拷贝**

![[Pasted image 20230223220916.png]]

## 4. Tableaux
#array 

### Déclaration et allocation

``` Java
int tableau[] = new int[50]; // déclaration et allocation
int[] tableau = new int[50];
int tab[];         // déclaration
tab = new int[50]; // allocation

float tableau[][] = new float[10][10];
int dim1[][] = new int[3][];
dim1[0]      = new int[4];
dim1[1]      = new int[9];
dim1[2]      = new int[2];
```

### L'initialisation

```java
int tableau[5]    = {10, 20, 30, 40, 50};
int tableau[3][2] = {{5, 1}, {6, 2}, {7, 3}};
int tableau[] = {10, 20, 30, 40, 50};
int[][] tabEntiers = {{1, 2, 3, 4, 5, 6}, {1, 2, 3, 4}, {1, 2, 3, 4, 5, 6, 7, 8, 9}};
int[] i1 = new int[]{1,2,3,4,5,7,8};
```

### Parcours

``` Java
for()
while()
Arrays.stream(arr).forEach(System.out::println)
```

# 转换

- [[String#^0e4978|基本类型与String的转换]]
- [[AbstractList#^c1c20b|数组与List的转换]]
- char 与 int 之间的转换
需要注意的是，当将一个较大的整数赋值给`char`时，可能会发生截断。因为`char`是16位的，它只能表示0到65535范围内的整数值。如果赋值的整数超出了这个范围，将会发生截断，只保留低16位的值。


# 包装类

## Integer 
#integer 

# 其他常见类型

## `BigDecimal BigInteger`

- La classe `BigDecimal` permet de réaliser de tels calculs du type numérique flottant, en permettant d'avoir le contrôle sur la précision
- il est préférable d'utiliser le constructeur attendant en paramètre la valeur sous forme de chaîne de caractères.

