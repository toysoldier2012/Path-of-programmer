#hashset

- [[LinkedHashSet]]

# 特点

- 按照添加内容的hash值排序
- 先通过 `hashCode()` 确定保存位置，再通过 equals 确定数值是否一致，再保存，全部一致就不保存
- 可以储存null值
- 初始长度为16
- 线程不安全
- 底层为HashMap

# 常用方法

## 增

```Java
boolean add(E e)
```

## 删

```Java

```

## 改

```Java

```

## 查

```Java
boolean contains(Object o)
```
