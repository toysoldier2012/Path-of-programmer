#variable 

#todo 翻译

# 类型

## 1. Type élémentaire/primitif
#primitivedatatype

| Type    | Désignation                                   | Longueur | Valeurs                                    | Commentaires                                                           |
| ------- | --------------------------------------------- | -------- | ------------------------------------------ | ---------------------------------------------------------------------- |
| boolean | valeur logique : true ou false                | 1 bit    | true ou false                              | pas de conversion possible vers un autre type, valeur par défaut false |
| byte    | octet signé                                   | 8 bits   | -128 à 127                                 |                                                                        |
| short   | entier court signé                            | 16 bits  | -32768 à 32767                             |                                                                        |
| char    | caractère Unicode                             | 16 bits  | `\u0000` à `\uFFFF`                        | entouré de cotes simples dans du code Java, valeur par défaut `\u0000` |
| int     | entier signé                                  | 32 bits  | -2147483648 à 2147483647                   |                                                                        |
| float   | virgule flottante simple précision (IEEE 754) | 32 bits  | 1.401e-045 à 3.40282e+038                  | avec un suffix f, par exemple 2f                                     |
| double  | virgule flottante double précision (IEEE 754) | 64 bits  | 2.22507e-308 à 1.79769e+308                | avec un suffix d, par exemple 2d                                     | 
| long    | entier long                                   | 64 bits  | -9223372036854775808 à 9223372036854775807 |                                                                        |

> [!question] 
> 请注意，这些长度是 Java 规范中定义的标准长度，但具体的实现可能会有所不同。此外，还有其他与平台相关的整数类型（如 `char` 的无符号版本 `char`）和大数字类型（如 `BigInteger` 和 `BigDecimal`），它们的长度可以根据具体的库和需求而变化。 

### Java 7

- La valeur des types entiers peut être exprimée dans le système binaire en utilisant le préfixe `0b` ou `0B`

``` java
byte valeurByte = (byte) 0b00010001;
short valeurShort = (short) 0b1001110111101;
int valeurInt = 0b1000;
long valeurLong = 0b010000101000101101000010100010110100001010001011010000101000101 L;
```

- Il est possible d'utiliser un ou plusieurs caractères tiret bas entre les chiffres qui composent un entier littéral

```java
int maValeur = 0b1001110_10001011_01001101_01000101;
long maxLong = 0x7fff_ffff_ffff_ffffL;
```

## 2. [[String]]

## 3. Tableaux
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

- [[Stream]]

```java
Arrays.stream(arr).forEach(System.out::println)
```

- [[Hello Java#^6c83db|Boucle]]

## 4. Objet

### 引用类别
#reference #gabagecollecter

#### 强引用

平时创建的引用类型皆为强引用
回收方式：当没有任何引用指向对象时，Garbage Collected（`System.gc`）会调用 finalize 方法

#### 软引用

通过 `SoftReference` 类包装

```Java
SoftReference<byte[]> softReference = new SoftReference<>(new byte[1024 * 1024 * 10]);
softReference.get();
```

空间不够时，会被自动回收
可以用于缓存

#### 弱引用

通过 `WeakReference` 类包装

```java
WeakReference<Person> personWeakReference = new WeakReference<>(new Person());  
System.gc();
```

被垃圾回收器发现时，直接回收
`ThreadLocal`

#### 虚引用

通过 `PhantomReference` 包装
无法获取被包装对象
堆外内存

### 拷贝类型

- **浅拷贝**：浅拷贝会在堆上创建一个新的对象（区别于引用拷贝的一点），不过，如果原对象内部的属性是引用类型的话，浅拷贝会直接复制内部对象的引用地址，也就是说拷贝对象和原对象共用同一个内部对象。
- **深拷贝** ：深拷贝会完全复制整个对象，包括这个对象所包含的内部对象。
- **引用拷贝**

![[Pasted image 20230223220916.png]]

# Comparaison

对于 [[Classe#`equals()`|equals()]]，正常来说只要 new 了，就不是一个对象，equals 就返回 false
但是 String 重写了 equals 方法，只比较内容

# Transformer

- [[String#^0e4978|基本类型与String的转换]]
- [[List#^d57335|数组与List的转换]]
- Char 与 int 之间的转换
需要注意的是，当将一个较大的整数赋值给 `char` 时，可能会发生截断。因为 `char` 是 16 位的，它只能表示 0 到 65535 范围内的整数值。如果赋值的整数超出了这个范围，将会发生截断，只保留低 16 位的值。

# Autoboxing/unboxing/Wrapper

## Integer 
#integer 

# 其他常见类型

## `BigDecimal` / `BigInteger`

- La classe `BigDecimal` permet de réaliser de tels calculs du type numérique flottant, en permettant d'avoir le contrôle sur la précision
- Il est préférable d'utiliser le constructeur attendant en paramètre la valeur sous forme de chaîne de caractères.

