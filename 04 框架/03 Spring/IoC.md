
# IoC, DI et Spring

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. Dans Spring, c'est par container IoC, il gère les objets comme des Beans, réalise **Dependency injection**, comme un relation entre les Beans

# Bean

如何获取 Bean
1. 通过 id
2. 通过 Class
3. 通过 id 以及 Class
4. 通过 bean 的父类或者接口

# Configuration de ficher applicationContext.xml

1. Alias du bean

On peut ajouter les alias de bean dans le paramètre "name"

2. Portée du Bean

La portée du bean par défaut est singleton, ou on peut le modifié en "prototype"

```java
<bean 
	id="beanDao" 
	name="bean beanBase" 
	scope="prototype" 
	class="com.xiaoyu.spring.dao.impl.BeanDaoImpl"
/>
```

3. Espace de nommage #TODO 

https://blog.csdn.net/hhx_echo/article/details/76095840

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

# Lifecycle de Bean

Implémenter l'interface "InitializingBean" et "DisposableBean" pour l'initialisation et la destruction

```java
public class BeanDaoImpl implements BeanDao, InitializingBean, DisposableBean {  
   @Override  
   public void test() {  
      System.out.println("BeanDaoImpl test....");  
   }  
  
   @Override  
   public void destroy() throws Exception {  
      System.out.println("destroy....");  
   }  
  
   @Override  
   public void afterPropertiesSet() throws Exception {  
      System.out.println("init....");  
   }  
}
```
