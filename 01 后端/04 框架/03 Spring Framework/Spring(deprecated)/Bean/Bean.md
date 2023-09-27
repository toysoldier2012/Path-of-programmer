#ioc #di

# IoC, DI et Spring

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. Dans Spring, c'est par container IoC, il gère les objets comme des Beans, réalise **Dependency injection**, comme un relation entre les Beans

**Dependency injection**, c'est un relation entre les Beans

~~# [[01 后端/04 框架/03 Spring Framework/Spring(deprecated)/Bean/DI par XML]]~~

~~# [[01 后端/04 框架/03 Spring Framework/Spring(deprecated)/Bean/Autowiring]]~~


# Factory mode

> [!todo] 
>  

Créer un `BeanFactory` par l'implémentation de l'interface `FactoryBean<>`

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

