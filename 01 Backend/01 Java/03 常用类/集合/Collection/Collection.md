
![[Pasted image 20230223231319.png]]

# 概述

## [[List]]

-   `ArrayList`： `Object[]` 数组
-   `Vector`：`Object[]` 数组
-   `LinkedList`： 双向链表(JDK1.6 之前为循环链表，JDK1.7 取消了循环)

## [[Set]]

-   `HashSet`(无序，唯一): 基于 `HashMap` 实现的，底层采用 `HashMap` 来保存元素
	-   `LinkedHashSet`: `LinkedHashSet` 是 `HashSet` 的子类，并且其内部是通过 `LinkedHashMap` 来实现的。有点类似于我们之前说的 `LinkedHashMap` 其内部是基于 `HashMap` 实现一样，不过还是有一点点区别的
-   `TreeSet`(有序，唯一): 红黑树(自平衡的排序二叉树)

## [[Queue]]

-   `PriorityQueue`: `Object[]` 数组来实现二叉堆
-   `ArrayQueue`: `Object[]` 数组 + 双指针

# 常用方法

## 增

```Java
boolean add(E e)
boolean addAll(Collection<? extends E> c)
```

## 删

```Java
boolean remove(Object o)
boolean removeAll(Collection<?> c)
void clear()
default boolean removeIf(Predicate<? super E> filter)
```

## 改

```Java
boolean retainAll(Collection<?> c)
```

## 查

```Java
boolean contains(Object o)
boolean containsAll(Collection<?> c)
Object[] toArray()
<T> T[] toArray(T[] a)
// 给定数组长度小于集合的大小，则会重新创建一个大小与集合相等的数组，并且传入数据
// 给定数组长度等于集合的大小，直接传入数据
// 给定数组长度大于集合的大小，多余的数组位用null代替
boolean isEmpty()
int size()
default Stream<E> stream() // 高级版的.iterator()
default Stream<E> parallelStream() // 并发Stream
```
