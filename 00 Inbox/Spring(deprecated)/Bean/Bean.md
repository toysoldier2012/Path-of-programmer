#ioc #di

# IoC, DI et Spring

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. Dans Spring, c'est par container IoC, il gère les objets comme des Beans, réalise **Dependency injection**, comme un relation entre les Beans

**Dependency injection**, c'est un relation entre les Beans

~~# [[DI par XML]]~~

~~# [[Autowiring]]~~

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

# Factory mode

> [!todo] 
>  

Créer un `BeanFactory` par l'implément de l'interface `FactoryBean<>`

```java
public class BeanDaoFactory implements FactoryBean<BeanDao> {  
   @Override  
   public BeanDao getObject() throws Exception {  
      return new BeanDaoImpl();  
   }  
  
   @Override  
   public Class<?> getObjectType() {  
      return BeanDao.class;  
   }  
}
```

Définir le bean dans applicationContext.xml

```xml
<bean id="beanDao" class="com.xiaoyu.spring.dao.factory.BeanDaoFactory"/>
```

