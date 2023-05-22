#list 

[[ArrayList]]
[[LinkedList]]
[[Vector]]

# 特点

- 
- 

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
