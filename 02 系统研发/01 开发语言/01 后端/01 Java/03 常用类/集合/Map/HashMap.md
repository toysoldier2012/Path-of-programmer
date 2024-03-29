#hashmap 

- [[LinkedHashMap]]

# 特点

- Map的主要实现类
- 线程不安全
- 能存储null
- 默认初始容量为16
- 扩容临界值为0.75 * 16 = 12
- 扩容为原来两倍 

# 重要细节

- 数组是 `HashMap` 的主体，链表则是主要为了解决哈希冲突而存在的（“拉链法”解决冲突）

- JDK1.8 以后在解决哈希冲突时有了较大的变化，当某一索引位置的元素，以链表形式存在
	- 大于8个，且当前数组长度
		- 大于64个，此索引位置元素改为红黑树存储。
		- 小于64个，那么会选择先进行数组扩容
	- 当树的结点个数小于6个时，再把树转换为链

# 常用方法

## 增

```Java
V put(K key, V value)
```

## 删

```Java

```

## 改

```Java

```

## 查

```Java
boolean containsKey(Object key)
boolean containsValue(Object value)
V get(Object key)
```
