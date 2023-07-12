#map

| Utilisation générale | Utilisation spécifique | Gestion des accès concurrents |
| -------------------- | ---------------------- | ----------------------------- |
| [[HashMap]]              | WeakHashMap            | [[Hashtable]]                     |
| [[TreeMap]]              | IdentityHashMap        | ConcurrentHashMap             |
| [[LinkedHashMap]]        | EnumMap                | ConcurrentSkipListMap         |

![[Pasted image 20230223231641.png]]

# 概览

-   `HashMap`： JDK1.8 之前 `HashMap` 由数组+链表组成的。当链表长度大于阈值时，将链表转化为红黑树，以减少搜索时间 

-   `LinkedHashMap`： `LinkedHashMap` 继承自 `HashMap`，在上面结构的基础上，增加了一条双向链表，使得上面的结构可以保持键值对的插入顺序。同时通过对链表进行相应的操作，实现了访问顺序相关逻辑。

-   `Hashtable`： 数组+链表组成的，数组是 `Hashtable` 的主体，链表则是主要为了解决哈希冲突而存在的

-   `TreeMap`： 红黑树（自平衡的排序二叉树）

# 特点

- 无序
- entry不可重复

# 常用方法

## 增

```Java
V put(K key, V value)
void putAll(Map<? extends K,? extends V> m)
```

## 删

```Java
V remove(Object key)
default boolean remove(Object key, Object value)
void clear()
```

## 改

```Java
default boolean replace(K key, V oldValue, V newValue)
default void replaceAll(BiFunction<? super K,? super V,? extends V> function)
default void forEach(BiConsumer<? super K,? super V> action)
default V computeIfAbsent(K key, Function<? super K,? extends V> mappingFunction)
default V computeIfPresent(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)
default V compute(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)
```

## 查

```Java
V get(Object key)
Set<K> keySet()
Collection<V> values()
Set<Map.Entry<K,V>> entrySet()
boolean containsKey(Object key)
boolean containsValue(Object value)
int size()
boolean isEmpty()
default V getOrDefault(Object key, V defaultValue)
```