#aop

通过 proxy 实现 #proxy 

# 基本步骤

## 1. pom.xml

```xml
<!-- https://mvnrepository.com/artifact/org.springframework/spring-aspects -->  
<dependency>  
	<groupId>org.springframework</groupId>  
	<artifactId>spring-aspects</artifactId>  
	<version>6.0.9</version>  
</dependency>  
<!-- https://mvnrepository.com/artifact/org.springframework/spring-aop -->  
<dependency>  
	<groupId>org.springframework</groupId>  
	<artifactId>spring-aop</artifactId>  
	<version>6.0.9</version>  
</dependency>
```

## 2. xml

``` xml
<?xml version="1.0" encoding="UTF-8"?>  
<beans xmlns="http://www.springframework.org/schema/beans"  
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
	xmlns:context="http://www.springframework.org/schema/context"  
	xmlns:aop="http://www.springframework.org/schema/aop"  
	  
	xsi:schemaLocation="  
	http://www.springframework.org/schema/beans  
	http://www.springframework.org/schema/beans/spring-beans.xsd  
	http://www.springframework.org/schema/context  
	http://www.springframework.org/schema/context/spring-context.xsd  
	http://www.springframework.org/schema/aop  
	http://www.springframework.org/schema/aop/spring-aop.xsd">  
  
	<context:component-scan base-package="com.xiaoyu.spring.aop"/>  
	  
	<aop:aspectj-autoproxy/>  
</beans>
```

## 3. 创建切面类

```java
import org.aspectj.lang.annotation.Aspect;  
import org.springframework.stereotype.Component;  
  
@Aspect  
@Component  
public class LogAspect {  
  
}
```

## 4. 设置切入点

```java
import org.aspectj.lang.annotation.Aspect;  
import org.springframework.stereotype.Component;  
  
@Aspect  
@Component  
public class LogAspect {  
	// @Before()  
	// @After()  
	// @AfterReturning  
	// @AfterThrowing  
	// @Around()  
}
```

## 5. 设置切入点表达式

![[Pasted image 20230618224915.png]]

```java
@Before(value = "execution(public int com.xiaoyu.spring" + 
		".aop.calculator.CalculatorImpl.*(..))")  
public void beforeMethod(){  

}
```
## 6. 完成通知

```java
import org.aspectj.lang.annotation.*;  
import org.springframework.stereotype.Component;  
  
@Aspect  
@Component  
public class LogAspect {  
	// @After()  
	// @AfterReturning  
	// @AfterThrowing  
	// @Around()  
  
	@Before(value = "execution(public int com.xiaoyu.spring" + 
		".aop.calculator.CalculatorImpl.*(..))")  
	public void beforeMethod(){  
		System.out.println("Before....");  
	}  
}
```

