
# 基本概念

通过已经创建的对象，获取其类及内部结构
框架 = 注解 + 反射 + 设计模式

# 创建方式

- 通过已知类的.Class属性获取
- 通过实例的.getClass()方法获取
- 通过Class类的.forName()方法获取
- 获取Classloader，再通过Classloader获取具体类的Class

# 可获取的内容

## 接口

``` Java
public Class<?>[] getInterfaces()
```

## 父类

``` Java
public Class<? Super T> getSuperclass()
```

## 构造器

``` Java
public Constructor<T>[] getConstructors()
public Constructor<T>[] getDeclaredConstructors()
public Constructor<T> getConstructor(@Nullable  Class<?>... parameterTypes)
public Constructor<T> getDeclaredConstructor(@Nullable  Class<?>... parameterTypes)
```

## 方法

``` Java
public Method[] getMethods()
public Method[] getDeclaredMethods()
public java.lang.reflect.Method getEnclosingMethod()
public Method getMethod(     
	@NonNls  @NotNull  String name,
	@Nullable  Class<?>... parameterTypes 
)
public Method getDeclaredMethod(
    @NonNls  @NotNull  String name,
    @Nullable  Class<?>... parameterTypes
)
```

## 属性

``` Java
public Field[] getFields()
public Field[] getDeclaredFields()
public Field getField(
	@NonNls  @NotNull  String name 
)
public Field getDeclaredField(
     @NonNls  @NotNull  String name 
)
```

## 注解

``` Java
public Annotation[] getAnnotations()
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
```

## 泛型

``` Java
public Type getGenericSuperclass()
public Type[] getGenericInterfaces()
```

## 包

``` Java
public Package getPackage()
```

# 动态代理

[[AOP]]
