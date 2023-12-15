#thread 

#todo 翻译

# Base

Program, Process, Thread

Java中至少有三个线程: 

- main线程
- gc线程
- 异常处理线程

# Création

## 1. Thread 类

1. 继承 Thread
2. 重写 run 方法
3. Lancer la méthode start

## 2. `Runnable` 接口

1. 实现接口
2. 重写 run 方法
3. 创建实现类对象
4. 创建 Thread 实例，传入实现类实例
5. Lancer la méthode start

## 3. `Callable` 接口

1. 实现接口
2. 重写 call 方法
3. 创建 Callable 实现类对象
4. 创建 FutureTask 对象，传入 Callable 实现类对象
5. 创建 Thread 实例，传入 FutureTask 对象

### 优势

- 每个线程都可以有返回值
- 可以抛出异常
- 支持泛型

## 4. 线程池

1. 创建线程池 `ExecutorService es = Executors.newFixedThreadPool(10)`

- `Executors` 是一个生成不同线程池的工具类
- `newFixedThreadPool` 固定数量线程的线程池
- `newCachedThreadPool` 根据需要创建线程的线程池
- `newScheduledThreadPool` 延迟/定期执行现成的线程池
- `newSingleThreadExecutor` 只有一个线程的线程池

2. 创建 `public Class Thread1 implements Runnable`

3. 执行

- Es.Execute (new Thread 1 ());
- Es. Submit 可以有返回值的执行任务，传入 Callable 实现类

## 常用方法

- `start()`
- `run()`
- `currentThread()`
- `getName` / `setName()`
- `yield()`  让权，不是阻塞
- `join()`  阻塞
- `stop()`
- `sleep()`
- `isAlive()`

## 线程生命周期

- NEW
- RUNNABLE
- BLOCKED
- WAITING
- TIMED_WAITING
- TERMINATED

## Daemon
#daemon

## Priorité

- 时间片（同优先级）
- 抢占式
	- 优先级设置
		优先级只代表抢占概率
- 常量
	- MAX_PRIORITY
	- MIN_PRIORITY
	- NORMAL_PRIORITY
- `setPriority()/getPriority(int p)`

# Thread safe

## Solution

- Le Mot clé `synchronized`
#synchronized 

Il permet de gérer l'accès concurrent aux variables et méthodes

```java
synchronized(lock){}
public synchronized void a(){}
```

- `volatile` 
#volatile 

Il précise que la variable peut être changé par un périphérique ou de manière asynchrone.

- `lock`
#lock

```java
ReentrantLock lock = new ReentrantLock();
lock.lock();
lock.unlock();
```

## 特殊案例

### 死锁
#deadlock 

通常情况下有三种解决方式
- 设置公共锁
- 固定获取锁的顺序
- 定时锁，在超时时间内重试获取锁

### 线程安全单例模式

# 线程通信

- wait()与notify/notifyAll()方法
	- 通过 monitor 控制阻塞/释放
- `wait()`
- `notify/notifyAll()`
