#array 

# Déclaration et allocation

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

# L'initialisation

```java
int tableau[5]    = {10, 20, 30, 40, 50};
int tableau[3][2] = {{5, 1}, {6, 2}, {7, 3}};
int tableau[] = {10, 20, 30, 40, 50};
int[][] tabEntiers = {{1, 2, 3, 4, 5, 6}, {1, 2, 3, 4}, {1, 2, 3, 4, 5, 6, 7, 8, 9}};
int[] i1 = new int[]{1,2,3,4,5,7,8};
```

# Parcours

- [[Stream]]

```java
Arrays.stream(arr).forEach(System.out::println)
```

- Foreach

# [[Conversion#^Ll6DJAsT||Conversion]]

## A stream

```java
Arrays.stream(array)
```

Que pour les types de `int[]`, `long[]`, `double[]`, ou `T extends Object[]`, aussi les types boxed

## A list

1. 使用 `Arrays.asList()`

```Java
ArrayList<T> arrayList = new ArrayList<T>(Arrays.asList(array));
```

不要只用

```Java
List<T> list = Arrays.asList(array);
```

因为 `asList()` 返回的列表的大小是固定的。事实上，返回的列表不是 `java.util.ArrayList`，而是定义在 `java.util.Arrays` 中一个私有静态类。我们知道 `ArrayList` 的实现本质上是一个数组，而 `asList()` 返回的列表是由原始数组支持的固定大小的列表。这种情况下，如果添加 ` add() ` 或删除 ` delete() ` 列表中的元素，程序会抛出异常 `UnsupportedOperationException`。

2. 使用 `Collections.addAll()`

```Java
List<String> list2 = new ArrayList<String>(arrays.length);
Collections.addAll(list2, arrays);
```

4. 使用 `for` 循环

```Java
String[] arrays = new String[]{"aa","bb","cc"};
List<String> list = new ArrayList<String>();

for(String str : arrays){
	list.add(str);
}
```
