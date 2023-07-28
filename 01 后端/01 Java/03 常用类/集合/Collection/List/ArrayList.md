#arraylist 

# 特点

- 底层为 Object[]
- 初始长度为 10
- 扩容为 1.5 倍，Java 8 之前扩容为 2 倍

# 常用方法

## 增

```Java

```

Adding element takes amortized constant time O(1)
Inserting takes O (n) time

## 删

```Java

```

Deleting takes O (n) time

## 改

```Java

```

## 查

```Java

``` 

Random access takes O(1) time
Searching takes O (n) time for unsorted array and O (log n) for a sorted one

# Complexité

| Prefix | Insert | Suffix | Remove first | Remove | Remove last | Search by index | Search by value |
| ------ | ------ | ------ | ------------ | ------ | ----------- | --------------- | --------------- |
| O(1)   | O (n)  | O (n)  | O (n)        | O (n)  | O (1)       | O (1)           | O (n)           | 
