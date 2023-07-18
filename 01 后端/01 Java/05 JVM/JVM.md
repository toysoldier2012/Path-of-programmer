
# [[内存解析]]

# Garbage Collected

1. `System.gc()`
2. Set object to null

Mark-and-Sweep
Copying
Mark-and-Compact

# Class Loader

用于把类装载到内存

## 1. `BootstrapClassLoader`

负责加载Java核心类库

## 2. `ExtensionClassLoader`

`%JRE_HOME%/lib/ext`中的jar包装载

## 3. `AppClassLoader`

负责java -classpath或java.class.path目录下的类与jar包的导入工作

## 4. 自定义Classloader
