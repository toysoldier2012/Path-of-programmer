#bean 

# Scope

Singleton
Prototype
Request
Session
Global-session

# Life cycle

## 1. Définir un Bean par l'annotation

## 2. Initialiser un Bean

## 3. 设置属性值:

## 4. `BeanNameAware` 和 `BeanFactoryAware`:

- 如果 Bean 实现了 `BeanNameAware` 接口，Spring 将 Bean 的 ID 传递给 `setBeanName()` 方法;
- 如果 Bean 实现了 `BeanFactoryAware` 接口，Spring 将调用 `setBeanFactory()` 方法，传入 `BeanFactory`。

## 5. BeanPostProcessor 前置处理:
    
在初始化前，Spring 将调用注册的 `BeanPostProcessor` 的 `postProcessBeforeInitialization()` 方法。

```java
public class BeanProcessor implements BeanPostProcessor {  
   @Override  
   public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {}  
  
   @Override  
   public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {  
      System.out.println("Before init | beanName = " + beanName + ", bean = " + bean);  
  
      return BeanPostProcessor.super.postProcessBeforeInitialization(bean, beanName);  
   }  
}
```

## 6. `InitializingBean`, `@PostConstruct` 和 `initMethod`:
    
- 如果 Bean 实现了 `InitializingBean` 接口，Spring 将调用它的 `afterPropertiesSet()` 方法。
- 如果有被 `@PostConstruct` 标记的方法，该方法会被调用，常用于执行一些初始化逻辑，比如开启资源、校验配置等
- 如果 Bean 定义了 `initMethod`，该方法也会被调用。

```java
public class BeanProcess implements InitializingBean {  
   private int id;  
  
   public BeanProcess() {  
      System.out.println("init....");  
   }  
  
   public void setId(int id) {  
      System.out.println("set id....");  
      this.id = id;  
   }  
	
	//postProcessBeforeInitialization

   @Override  
   public void afterPropertiesSet() throws Exception {  
      System.out.println("after properties set...");  
   }

   @PostConstruct
   public void doSomething() {
         System.out.println("post construct method....");  
   }
  
   public void initMethod(){  
      System.out.println("init method....");  
   }  
   
}
```

## 7. `BeanPostProcessor` 后置处理:
    
- 在初始化后，Spring 将调用注册的 `BeanPostProcessor` 的 `postProcessAfterInitialization()` 方法。

```java
public class BeanProcessor implements BeanPostProcessor {  
   @Override  
   public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {  
      System.out.println("After init | beanName = " + beanName + ", bean = " + bean);  
      return BeanPostProcessor.super.postProcessAfterInitialization(bean, beanName);  
   }  
  
   @Override  
   public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {}  
}
```

## 8. Bean 的使用:
    
此时，Bean 已经准备好被应用程序使用。

## 9. `DisposableBean`，`@PreDestroy` 和 `destroyMethod`:
    
- 当容器关闭时，如果 Bean 实现了 `DisposableBean` 接口，Spring 将调用它的 `destroy()` 方法。
- 如果 Bean 定义了 `destroyMethod`，该方法也会被调用。
- `@PreDestroy` 用于标记在 Spring 容器销毁 Bean 之前执行的方法，通常用于执行一些清理工作，比如关闭资源、清理缓存等。

```java
public class BeanProcess implements DisposableBean {  
	//postProcessAfterInitialization
   
   public void test(){  
      System.out.println("test....");  
   }  
  
   @Override  
   public void destroy() throws Exception {  
      System.out.println("destroy....");  
   }  
  
   public void destroyMethod(){  
      System.out.println("destroy method....");  
   }
   
   @PreDestroy
   public void doSomething() {
         System.out.println("pre destroy method....");  
   }
}
```

## 10. 销毁 Bean:
    
最后，Bean 的实例将被销毁，不再可用。
