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