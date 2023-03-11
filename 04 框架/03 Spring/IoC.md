
# IoC, DI et Spring

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. Dans Spring, c'est par container IoC, il gère les objets comme des Beans, réalise **Dependency injection**, comme un relation entre les Beans

# Fichier de configuration `applicationContext.xml`

## 1. Namespace

^e4c41f

```xml
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       xsi:schemaLocation="  
        http://www.springframework.org/schema/beans        
        http://www.springframework.org/schema/beans/spring-beans.xsd">
</beans>
```

> [!todo] 
> https://blog.csdn.net/hhx_echo/article/details/76095840 

## 2. Bean

### bean的组成部分

```xml
<bean 
	id="beanDao" 
	name="bean beanBase" 
	scope="prototype" 
	class="com.xiaoyu.spring.dao.impl.BeanDaoImpl"
/>
```

1. **id**
2. **Alias du bean**: On peut ajouter les alias de bean dans le paramètre "name"
3. **Portée du Bean**: La portée du bean par défaut est singleton, ou on peut le modifié en "prototype", dans `WebApplicationContext`, il y a deux autre portées, request et session

### 如何获取 Bean

``` java
ApplicationContext classPathXmlApplicationContext = new ClassPathXmlApplicationContext("applicationContext.xml");  
Actor actor = (Actor) classPathXmlApplicationContext.getBean("actorB");  
actor.test();  
System.out.println(actor);
```

1. 通过 id
2. 通过 Class
3. 通过 id 以及 Class
4. 通过 bean 的父类或者接口

### Lifecycle de Bean

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

1. Static Factory

```java
<bean 
	id="beanDaoFactory" 
	name="bean" 
	scope="singleton" 
	class="com.xiaoyu.spring.dao.impl.BeanDaoImplFactory"
	factory-method="getBeanDao"
/>
```

2. FactoryBean

Créer un "BeanFactory" implémente FactoryBean<>

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

Définir le bean dans applicationContext. Xml

```xml
<bean id="beanDao" class="com.xiaoyu.spring.dao.factory.BeanDaoFactory"/>
```

