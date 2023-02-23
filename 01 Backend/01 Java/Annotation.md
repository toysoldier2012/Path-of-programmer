
# Hello Annotation

1. 以@开头
2. 类型
	- 生成文档相关
	- 编译相关
		- `@override`
		- `@Deprecated`
		- `@suppressWarnings()`，必须输入值，如“unused”
	- 配置文件相关

# 自定义注解

## 1. `@interface`关键字

## 2. 成员变量

- 以无参方法的形式定义成员变量，通过返回值确定类型

``` Java
String a();
```

- 只能有8种类型，String、Class、enum、Annotation，及其数组类型
- 如果只有一个成员变量，建议用value()作为成员变量名，如String value()，使用注解时

``` java
@MyAnnotation(value = "abc")
@MyAnnotation("abc")
```

- 可以使用default声明默认值，如`String value() default "hello"`，随后也可以在使用注解时更改

# 元注解

修饰其他注解的注解

## 类型

### Retention

指定Annotation的生命周期

成员变量RetentionPolicy
- SOURCE
- CLASS
- RUNTIME

### Target

指定可修饰元素类型

成员变量ElementType
- TYPE
- FIELD
- METHOD
- PARAMETER
- CONSTRACTOR
- LOCAL_VARIABLE
- PACKAGE

### Documented

是否出现在文档中

### Inherited

是否继承