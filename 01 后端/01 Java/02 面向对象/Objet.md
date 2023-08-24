
#object


# 引用类别
#reference #gabagecollecter

#### 强引用

平时创建的引用类型皆为强引用
回收方式：当没有任何引用指向对象时，Garbage Collected（`System.gc`）会调用 finalize 方法

#### 软引用

通过 `SoftReference` 类包装

```Java
SoftReference<byte[]> softReference = new SoftReference<>(new byte[1024 * 1024 * 10]);
softReference.get();
```

空间不够时，会被自动回收
可以用于缓存

#### 弱引用

通过 `WeakReference` 类包装

```java
WeakReference<Person> personWeakReference = new WeakReference<>(new Person());  
System.gc();
```

被垃圾回收器发现时，直接回收
`ThreadLocal`

#### 虚引用

通过 `PhantomReference` 包装
无法获取被包装对象
堆外内存

# 拷贝类型

- **浅拷贝**：浅拷贝会在堆上创建一个新的对象（区别于引用拷贝的一点），不过，如果原对象内部的属性是引用类型的话，浅拷贝会直接复制内部对象的引用地址，也就是说拷贝对象和原对象共用同一个内部对象。
- **深拷贝** ：深拷贝会完全复制整个对象，包括这个对象所包含的内部对象。
- **引用拷贝**

![[Pasted image 20230223220916.png]]
