#thread 
#todo 翻译

# 基本概念

#todo 程序，进程与线程

Java中至少有三个线程: 

- main线程
- gc线程
- 异常处理线程
 
#todo 并行与并发


## 线程生命周期

- NEW
- RUNNABLE
- BLOCKED
- WAITING
- TIMED_WAITING
- TERMINATED


# 线程安全

## 解决方式

- 同步
	- 同步代码块synchronized(lock){}
	- 同步方法public synchronized void a(){}

- Lock
	- ReentrantLock lock = new ReentrantLock();
	- lock.lock();
	- lock.unlock();
		- 这里lock就是monitor

## 特殊案例

- 死锁
#deadlock 

- 线程安全单例模式


# 线程通信

- wait()与notify/notifyAll()方法
	- 通过 monitor 控制阻塞/释放

# 线程调度

- 时间片（同优先级）
- 抢占式
	- 优先级设置
		优先级只代表抢占概率
- 常量
	- MAX_PRIORITY
	- MIN_PRIORITY
	- NORMAL_PRIORITY
- `setPriority()/getPriority(int p)`

# 创建

## 1. Thread类

1. 继承Thread
2. 重写run方法
3. Lancer la méthode start

### 常用方法

- `start()`
- `run()`
- `currentThread()`
- `getName`/`setName()`
- `yield()`  让权，不是阻塞
- `join()`  阻塞
- `stop()`
- `sleep()`
- `isAlive()`

## 2. Runnable接口

1. 实现接口
2. 重写run方法
3. 创建实现类对象
4. 创建Thread实例，传入实现类实例
5. Lancer la méthode start

## 3. Callable接口

1. 实现接口
2. 重写call方法
3. 创建Callable实现类对象
4. 创建FutureTask对象，传入Callable实现类对象
5. 创建Thread实例，传入FutureTask对象

### 优势

- 每个线程都可以有返回值
- 可以抛出异常
- 支持泛型

## 4. 线程池

1. 创建线程池`ExecutorService es = Executors.newFixedThreadPool(10)`

- `Executors` 是一个生成不同线程池的工具类
- `newFixedThreadPool` 固定数量线程的线程池
- `newCachedThreadPool` 根据需要创建线程的线程池
- `newScheduledThreadPool` 延迟/定期执行现成的线程池
- `newSingleThreadExecutor` 只有一个线程的线程池

2. 创建`public Class Thread1 implements Runnable`

3. 执行

- es.execute(new Thread1());
- es.submit 可以有返回值的执行任务，传入Callable实现类

### 优势









