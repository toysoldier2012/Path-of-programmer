#collection 

![[Pasted image 20230223231319.png]]

# Préambule

1. [[List]]
2. [[Set]]
3. [[Queue]]

# 常用方法

Certains méthodes lèvent `UnsupportedOperationException` car leur implémentation est optionnelle

## 增

```Java
boolean add(E e)
boolean addAll(Collection<? extends E> c)
```

## 删

```Java
void clear()

boolean remove(Object o)
boolean removeAll(Collection<?> c)
default boolean removeIf(Predicate<? super E> filter)

boolean retainAll(Collection<?> c)
```

## 查

```Java
boolean contains(Object o)
boolean containsAll(Collection<?> c)
boolean isEmpty()

int size()
```

## 其他

```java
Iterator<E> iterator()

Object[] toArray()
<T> T[] toArray(T[] a)

default Stream<E> stream() // 高级版的.iterator()
default Stream<E> parallelStream() // 并发Stream
```
