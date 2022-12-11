# 1. [[基础知识]]

# 2. [[通用语法]]

# 3. [[面向对象]]

# 4. 常用类

## [[集合]]

## 包装类

## 字符串

- String类

	- 类特性

		- 不可被继承
		- Comparable接口
		- Serializable接口

	- 对象特性

		- 不可变

	- 转换

		- 与基本数据类型，包装类的转换

			- String --> 基本，xxx.parceXxx()
			- 基本 --> String，String.valueOf()

		- 与char类型

			- toCharArray()
			- String(char[])

		- 与byte类型

			- getBytes()
			- String(byte[])

	- 常用方法

		- compareTo()

		  a value 0 if the argument string is equal to this string; 
		  a value less than 0 if this string is lexicographically less than the string argument; 
		  a value greater than 0 if this string is lexicographically greater than the string argument.
		  
		- length()

- StringBuffer

	- 1. 线程安全
2. 扩容为2倍
3. 初始容量为16

- StringBuilder

	- 线程不安全

### IO流

- 

	- 分类

		- 数据单位

			- 字节流
			- 字符流

		- 流向

			- 输入流
			- 输出流

		- 角色

			- 节点流
			- 处理流

	- 以及RandomAccessFile

### 次要

- Object

	- equals()
	- toString()

- System
- Arrays
- Math
- Scanner
- 比较器

	- Comparable接口
	- Comparator接口

### 其他

- 时间日期类

	- 过时

		- System.currentTimeMillis() 1.0
		- Date

			- util包中的Date 1.0
			- sql包中的Date 1.1

		- Calendar 1.1
		- SimpleDateFormat 1.1

	- LocalDate, LocalTime, LocalDateTime 1.8
	- Instant 1.8
	- DateTimeFormatter 1.8

- BigInteger
- BigDecimal
- 自定义数组的工具类
- JavaBean
- File类

## 进阶

### 枚举

- 需要定义一系列常量时，强烈建议使用枚举
- 创建

	- Enum关键字
	- .values()方法

		- 返回一个包含所有值的数组

- 实现接口

### 异常

- 分类

	- 运行时异常

		- java.lang.StringIndexOutOfBoundsException

	- 编译时异常

- 步骤

	- 抛出异常

		- throw

	- 处理异常

		- throws
		- try...catch...finally

### 泛型

- 泛型在Collection中的应用

	- 1. 确保数据添加类型安全
	- 2. 简化读取步骤，不再需要强转

- 泛型类
- 泛型接口
- 泛型方法
- 泛型与继承
- 通配符

	- 读写数据

		- List<?>

			- 除了null，不允许添加元素
			- 可以读取数据

		- 有限制条件的通配符

			- List<? extends Person>设置上线
			- List<? super Person>设置下限

### 多线程

- 基本概念

	- 程序，进程与线程
	- Java中至少有三个线程
- main线程
- gc线程
- 异常处理线程
	- 并行与并发
	- 线程生命周期

		- NEW
		- RUNNABLE
		- BLOCKED
		- WAITING
		- TIMED_WAITING
		- TERMINATED

- 创建

	- Thread类

		- 流程

			- 1. 继承Thread
			- 2. 重写run方法
			- 3. 调用start方法

				- 可以开启一个新线程，并在新线程中执行run方法

		- 常用方法

			- start()
			- run()
			- currentThread()
			- getName/setName()
			- yield()  让权，不是阻塞
			- join()  阻塞
			- stop()
			- sleep()
			- isAlive()

	- Runnable接口

		- 流程

			- 1. 实现接口
			- 2. 重写run方法
			- 3. 创建实现类对象
			- 4. 创建Thread实例，传入实现类实例

	- Callable接口

		- 流程

			- 1. 实现接口
			- 2. 重写call方法
			- 3. 创建Callable实现类对象
			- 4. 创建FutureTask对象，传入Callable实现类对象
			- 5. 创建Thread实例，传入FutureTask对象

		- 优势

			- 每个线程都可以有返回值
			- 可以抛出异常
			- 支持泛型

	- 线程池

		- 流程

			- 1. ExecutorService es = Executors.newFixedThreadPool(10)

				- Executors是一个生成不同线程池的工具类
newFixedThreadPool 固定数量线程的线程池
newCachedThreadPool 根据需要创建线程的线程池
newScheduledThreadPool 延迟/定期执行现成的线程池
newSingleThreadExecutor 只有一个线程的线程池

			- 2. class Thread1 implements Runnable
			- 3. es.execute(new Thread1());

				- es.submit 可以有返回值的执行任务，传入Callable实现类

		- 优势

- 线程调度

	- 时间片（同优先级）
	- 抢占式

		- 优先级设置
优先级只代表抢占概率

			- 常量

				- MAX_PRIORITY
				- MIN_PRIORITY
				- NORMAL_PRIORITY

			- setPriority()/getPriority(int p)

- 线程安全

	- 解决方式

		- 同步

			- 同步代码块
synchronized(lock){}
			- 同步方法
public synchronized void a(){}

		- Lock

			- ReentrantLock lock = new ReentrantLock();
lock.lock();
lock.unlock();

				- 这里lock就是monitor

	- 特殊案例

		- 死锁
		- 线程安全单例模式

- 线程通信

	- wait()与notify/notifyAll()方法

		- 通过monitor控制阻塞/释放

### 注解

- 以@开头
- 类型

	- 生成文档相关
	- 编译相关

		- @override
		- @Deprecated
		- @suppressWarnings()
必须输入值，如“unused”

	- 配置文件相关

- 自定义注解

	- @interface关键字，继承Annotation接口
	- 成员变量

		- 1. 以无参方法的形式定义成员变量，通过返回值确定类型
		- 2. 只能有8种类型，String、Class、enum、Annotation，及其数组类型
		- 3. 如果只有一个成员变量，建议用value()作为成员变量名，如String value()，使用注解时@MyAnnotation(value = "abc")
		- 4. 可以使用default声明默认值，如String value() default "hello"，随后也可以在使用注解时更改

- 元注解

	- 修饰其他注解的注解
	- 类型

		- Retention

			- 指定Annotation的生命周期
			- 成员变量RetentionPolicy

				- SOURCE
				- CLASS
				- RUNTIME

		- Target

			- 指定可修饰元素类型
			- 成员变量ElementType

				- TYPE
				- FIELD
				- METHOD
				- PARAMETER
				- CONSTRACTOR
				- LOCAL_VARIABLE
				- PACKAGE

		- Documented

			- 是否出现在文档中

		- Inherited

			- 是否继承

### 反射

- 基本概念

	- 通过已经创建的对象，获取其类
	- 框架 = 注解 + 反射 + 设计模式

- 三种创建方式

	- 1. 通过已知类的.Class属性获取
	- 2. 通过实例的.getClass()方法获取
	- 3. 通过Class类的.forName()方法获取
	- 4. 获取Classloader，再通过Classloader获取具体类的Class

- 可获取的内容

	- 

		- 接口

			- public Class<?>[] getInterfaces()
			- 
			- 

		- 父类

			- 
			- public Class<? Super T> getSuperclass()

		- 构造器

			- public Constructor<T>[] getConstructors()
public Constructor<T>[] getDeclaredConstructors()
			- public Constructor<T> getConstructor(     
    @Nullable  Class<?>... parameterTypes
)

public Constructor<T> getDeclaredConstructor(
     @Nullable  Class<?>... parameterTypes 
)

		- 方法

			- public Method[] getMethods()
public Method[] getDeclaredMethods()
public java.lang.reflect.Method getEnclosingMethod()
			- public Method getMethod(     
    @NonNls  @NotNull  String name,
    @Nullable  Class<?>... parameterTypes 
)

public Method getDeclaredMethod(
    @NonNls  @NotNull  String name,
    @Nullable  Class<?>... parameterTypes
)

		- 属性

			- public Field[] getFields()
public Field[] getDeclaredFields()
			- public Field getField(
     @NonNls  @NotNull  String name 
)

public Field getDeclaredField(
     @NonNls  @NotNull  String name 
)

		- 注解

			- public Annotation[] getAnnotations()
public Annotation[] getDeclaredAnnotations()
public A[] getAnnotationsByType(
     @NotNull  Class<A> annotationClass 
)
public A[] getDeclaredAnnotationsByType(
     @NotNull  Class<A> annotationClass 
)
			- public A getAnnotation(
     @NotNull  Class<A> annotationClass 
)

public A getDeclaredAnnotation(
     @NotNull  Class<A> annotationClass 
)

		- 泛型

			- public Type getGenericSuperclass()
public Type[] getGenericInterfaces()

		- 包

			- public Package getPackage()

- 动态代理

	- AOP

### lambda

- 简化函数接口
- (parameters) -> expression 
或 (parameters) ->{ statements; }

	- 最多只能有两个参数

- 省略规则

	- 参数

		- 可以省略参数类型
		- 如果只有一个参数，可以同时省略参数类型和小括号

	- 方法体

		- 如果只有一条语句，可以省略大括号
		- 如果只有一条return语句，可以省略return和大括号

	- 通过::继续简化

		- 静态方法引用（static method）语法：classname::methodname 例如：Person::getAge
		- 对象的实例方法引用语法：instancename::methodname 例如：System.out::println
		- 对象的超类方法引用语法： super::methodname
		- 类构造器引用语法： classname::new 例如：ArrayList::new
		- 数组构造器引用语法： typename[]::new 例如： String[]:new

## JDBC

### 基本流程

- 导入java.sql包
- 创建Driver对象

	- 方式

		- JDBC-ODBC桥方式
		- 纯Java驱动

- 创建Connection对象
- 创建PreparedStatement对象
- 执行SQL语句
- 使用ResultSet对象
- 关闭ResultSet对象
- 关闭PreparedStatement对象
- 关闭Connection对象
- 结束

### 通用操作

- 增删改
- 查询
- Apache-DBUtils包

### 事务处理

- 什么情况下需要事务处理

	- 当一个完整的事务中有多个操作步骤时，需要多个步骤共进退，就要考虑通过事务解决，并且多个步骤要同时提交

- 会导致自动提交的步骤

	- DDL操作一旦执行，就会自动提交

		- 无法通过命令解决

	- DML默认自动提交，需要设置autocommit属性

		- connection.setAutoCommit(false)

	- 关闭连接会导致自动提交

		- 只创建一个connection

- 其他操作

	- 手动提交/回滚数据

		- connection.commit()
		- connection.rollback()

	- 在close Connection时，恢复自动提交

		- connection.setAutoCommit(true)

- ACID属性

	- 原子性Atomicity
	- 一致性Consistency
	- 隔离性Isolation

		- 由于数据库字段可以被多个事务同时操作，因此可能会出现数据不一致现象

			- lectures inconsistantes

			  脏读，T1读取了一个字段，T2更新了此字段，但没有提交，T1再次读取，字段发生了变化
			  
			  READ UNCOMMITTED，会导致这个问题，允许读取未提交数据
			  READ COMMITTED可以避免，只允许读取其他事务已提交的数据
			  
			  
			- Lectures non répétitibles

			  不可重复读，T1读取了一个字段，T2更新了该字段，T1再次读取该字段，数据发生变化
			  
			  REPEATABLE READ可以解决这个问题，在T1事务持续期间，禁止其他事务对此字段的操作
			  
			- Lecture fantôme

			  幻读，T1读取了一个表中的某字段，其他事务在该表中插入了一些新数据，T1再次读取就会多出几行
			  
			  SERIALIZABLE可以解决，在某事务读取一个表中的字段时，禁止其他事务对该表的操作
			  
			  
	- 持久性Durability

### 数据库连接池

- 必要性
- 第三方连接池

	- c3p0
	- druid
	- dbcp

## 框架

## JVM

### 内存解析

- 对象
- 数组

### ClassLoader

- 用于把类装载到内存
- 类型

	- Bootstrap Classloader

		- 负责加载Java核心类库

	- Extension Classloader(PlatformClassLoader)

		- jar包装载

	- System Classloader(AppClassLoader)

		- 负责java -classpath或java.class.path目录下的类与jar包的导入工作

	- 自定义Classloader

## 设计模式

### MVC

### 23种设计模式

- 单例模式

	- 懒汉式
	- 饿汉式

- 代理模式
- 工厂模式
- 迭代器模式

