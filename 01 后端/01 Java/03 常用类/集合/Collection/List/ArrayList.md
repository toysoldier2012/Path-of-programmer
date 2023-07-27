
# 特点

- 底层为Object[]
- 初始长度为10
- 扩容为1.5倍，Java8之前扩容为2倍

# 转换
^d57335

## 数组转 `List`

1. 使用 `Arrays.asList()`

```Java
ArrayList<String> arrayList = new ArrayList<String>(Arrays.asList(arrays));
```

不要只用

```Java
List<String> list = Arrays.asList(arrays);
```

因为 `asList()` 返回的列表的大小是固定的。事实上，返回的列表不是 `java.util.ArrayList`，而是定义在 `java.util.Arrays` 中一个私有静态类。我们知道 `ArrayList` 的实现本质上是一个数组，而 `asList()` 返回的列表是由原始数组支持的固定大小的列表。这种情况下，如果添加 ` add() ` 或删除 ` delete() ` 列表中的元素，程序会抛出异常 `UnsupportedOperationException`。

2. 使用 `Collections.addAll()`

```Java
List<String> list2 = new ArrayList<String>(arrays.length);
Collections.addAll(list2, arrays);
```

3. 使用 `Stream`

```java
List<String> list = Stream.of(array).collect(Collectors.toList()); 

List<String> list = Arrays.stream(array).collect(Collectors.toList()); 
```

4. 使用 `for` 循环

```Java
String[] arrays = new String[]{"aa","bb","cc"};
List<String> list = new ArrayList<String>();

for(String str : arrays){
	list.add(str);
}
```

## `List` 转数组

1. `toArray` 方法

```Java
String[] array1 = list.toArray(new String[0]);
String[] array3 = list.toArray(new String[list.size()]);
```

2. 使用 `stream`

```Java
String[] array2 = list.stream().toArray(String[]::new);
```

# 常用方法

## 增

```Java

```

Adding element takes amortized constant time O(1)
Inserting takes O(n) time

## 删

```Java

```

Deleting takes O(n) time

## 改

```Java

```

## 查

```Java

``` 

Random access takes O(1) time
Searching takes O(n) time for unsorted array and O(log n) for a sorted one
