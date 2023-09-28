#bean 

# Scope

Singleton
Prototype
Request
Session
Global-session

# Life cycle

Implémenter l'interface `InitializingBean` et `DisposableBean` pour l'initialisation et la destruction.
Ordre est suivante:

```java
public class BeanProcess implements InitializingBean, DisposableBean {  
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
  
   public void initMethod(){  
      System.out.println("init method....");  
   }  
   
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
}
```

le `BeanPostProcessor` effectue sur tous les beans dans le fichier `applicationContext.xml`
`bean` est le bean actuel et `beanName` est l'id de bean

```java
public class BeanProcessor implements BeanPostProcessor {  
   @Override  
   public Object postProcessAfterInitialization(Object bean, String beanName) throws BeansException {  
      System.out.println("After init | beanName = " + beanName + ", bean = " + bean);  
      return BeanPostProcessor.super.postProcessAfterInitialization(bean, beanName);  
   }  
  
   @Override  
   public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeansException {  
      System.out.println("Before init | beanName = " + beanName + ", bean = " + bean);  
  
      return BeanPostProcessor.super.postProcessBeforeInitialization(bean, beanName);  
   }  
}
```
