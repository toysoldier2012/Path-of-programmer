
- [[Set]]
- [[Queue]]

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

# 两种排序方式

Lambda : unsortedList.sort(Comparator.comparing(String::toString))
stream : unsortedList.stream().sorted((s1, s2) -> 	s1.compareTo(s2)).collect(Collectors.toList())