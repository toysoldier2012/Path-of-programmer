
# [[内存解析]]

### ClassLoader

- 用于把类装载到内存
- 类型
	- Bootstrap ClassLoader
		- 负责加载Java核心类库
	- Extension ClassLoader(PlatformClassLoader)
		- jar包装载
	- System ClassLoader(AppClassLoader)
		- 负责java -classpath或java.class.path目录下的类与jar包的导入工作
	- 自定义Classloader

***

# [[Garbage Collected]]

1. System.gc()
2. Set object to null

***