#list 

| Utilisation générale | Utilisation spécifique | Gestion des accès concurrents |
| -------------------- | ---------------------- | ----------------------------- |
| [[ArrayList]]        | CopyOnWriteArrayList   | [[Vector]]                    |
| [[LinkedList]]       |                        | Stack                         |
|                      |                        | CopyOnWriteArrayList          |

# 特点

# 排序

1. 可以使用 `Collections` 类的 `sort()` 方法对 `List` 进行排序。

```java
Collection.sort(unsortedList)
```

如果要对自定义对象的列表进行排序，需要确保对象实现了 `Comparable` 接口，并实现了 `compareTo()` 方法，或者在 `sort()` 中指定一个 `Comparator` #comparable #comparator 

``` java
Collections.sort(arrayList, (o 1, o 2) -> o 2.compareTo(o 1));
Collections.sort(arrayList, Comparator.reverseOrder());
```

2. 从 Java 8开始，`List` 接口提供了一个默认方法 `sort()`，可以直接在列表上进行排序。这种方法要求列表的元素类型实现了 `Comparable` 接口或传入一个自定义的 `Comparator` 对象来定义排序规则。 #comparable #comparator 

```java
unsortedList.sort(null)
unsortedList.sort(Comparator.comparing(String::toString))
```

3. 通过 stream 处理排序

``` java
stream : unsortedList.stream().sorted((s1, s2) -> 	s1.compareTo(s2)).collect(Collectors.toList())
```

# 比较

只比较每个元素是否相同

# 转换
^d57335

## 数组转 `List`

1. 使用 `Arrays.asList()`

```Java
ArrayList<String> arrayList = new ArrayList<String>(Arrays.asList(arrays));
```

2. 使用 `Collections.addAll()`

```Java
List<String> list2 = new ArrayList<String>(arrays.length);
Collections.addAll(list2, arrays);
```

3. `Stream`

```java
List<String> list = Stream.of(array).collect(Collectors.toList()); 

List<String> list = Arrays.stream(array).collect(Collectors.toList()); 
```

4. 使用 `for` 循环

```Java
String[] arrays = new String[]{"aa","bb","cc"};
List<String> list = new ArrayList<String>();

for(String str : arrays){
	list.add(str);
}
```

5. 使用 `asList()`

```Java
List<String> list = Arrays.asList(arrays);
```

同一样使用了 `asList()` 方法。这不是最好的，因为 `asList()` 返回的列表的大小是固定的。事实上，返回的列表不是 `java.util.ArrayList`，而是定义在 `java.util.Arrays` 中一个私有静态类。我们知道 `ArrayList` 的实现本质上是一个数组，而 `asList()` 返回的列表是由原始数组支持的固定大小的列表。这种情况下，如果添加 ` add() ` 或删除 ` delete() ` 列表中的元素，程序会抛出异常 `UnsupportedOperationException`。

## `List` 转数组

```	
// 第一种方式，推荐
String[] array1 = list.toArray(new String[0]);

// 第二种方式，推荐
String[] array2 = list.stream().toArray(String[]::new);

// 第三种方式
String[] array3 = list.toArray(new String[list.size()]);
```

# 常用方法

## 增

```Java
void add(int index, E element)
boolean addAll(int index, Collection<? extends E> c)
```

## 删

```Java
E remove(int index)
```

## 改

```Java
E set(int index, E element)
default void sort(Comparator<? super E> c)
default void replaceAll(UnaryOperator<E> operator)
```

## 查

```Java
List<E> subList(int fromIndex, int toIndex)
E get(int index)
int indexOf(Object o)
int lastIndexOf(Object o)
```
