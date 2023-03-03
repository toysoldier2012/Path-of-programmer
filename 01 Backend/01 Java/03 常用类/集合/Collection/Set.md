
> [!question]
> Q: 比较 HashSet、LinkedHashSet 和 TreeSet 三者的异同 #D1 
> -   `HashSet`、`LinkedHashSet` 和 `TreeSet` 都是 `Set` 接口的实现类，都能保证元素唯一，并且都不是线程安全的。
> -  `HashSet`、`LinkedHashSet` 和 `TreeSet` 的主要区别在于底层数据结构不同。`HashSet` 的底层数据结构是哈希表（基于 `HashMap` 实现）。`LinkedHashSet` 的底层数据结构是链表和哈希表，元素的插入和取出顺序满足 FIFO。`TreeSet` 底层数据结构是红黑树，元素是有序的，排序的方式有自然排序和定制排序。
> - 底层数据结构不同又导致这三者的应用场景不同。`HashSet` 用于不需要保证元素插入和取出顺序的场景，`LinkedHashSet` 用于保证元素的插入和取出顺序满足 FIFO 的场景，`TreeSet` 用于支持对元素自定义排序规则的场景

[[HashSet]]
[[TreeSet]]
 
# 特点

- 无序性（但不等于随机性）
- 元素不可重复的列表

# 常用方法

## 增

```Java

```

## 删

```Java

```

## 改

```Java

```

## 查

```Java

```
