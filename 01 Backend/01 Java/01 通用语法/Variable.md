
# 类型

## 1. 基本类型

## 2. String类型

## 3. 引用类型

### 强引用

1. 平时创建的引用类型皆为强引用
2. 回收方式：当没有任何引用指向对象时，Garbage Collected（System.gc）会调用finalize方法

### 软引用

1. 通过SoftReference类包装

```Java
SoftReference<byte[]> softReference = new SoftReference<>(new byte[1024 * 1024 * 10]);
softReference.get();
```

2. 空间不够时，会被自动回收
3. 可以用于缓存

### 弱引用

1. 通过WeakReference类包装

```Java
WeakReference<Person> personWeakReference = new WeakReference<>(new Person());  
System.gc();
```

2. 被垃圾回收器发现时，直接回收
3. [[ThreadLocal]]

### 虚引用

1. 通过PhantomReference包装
2. 无法获取被包装对象
3. [[堆外内存]]

***

# 类型转换

***

# 其他常见类型

BigDecimal BigInteger

***

