
# IoC, DI et Spring

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. Dans Spring, c'est par container IoC, il gère les objets comme des Beans, réalise **Dependency injection**, comme un relation entre les Beans

# Hello Spring

![[Pasted image 20230111150913.png]]

1. pom.xml

```xml
<dependency>  
  <groupId>org.springframework</groupId>  
  <artifactId>spring-context</artifactId>  
  <version>6.0.3</version>  
</dependency>
```

2. applicationContext.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>  
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       xsi:schemaLocation="  
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">  
  
    <!-- bean definitions here -->  
	<bean id="beanDao" class="com.xiaoyu.spring.dao.impl.BeanDaoImpl"/>  
	  
	<bean id="beanService" class="com.xiaoyu.spring.service.impl.BeanServiceImpl">  
	    <property name="beanDao" ref="beanDao"/>  
	</bean>
</beans>
```

3. Dans "beanService", déclarer la variable "beanDao" et créer "setBeanDao"

```Java
public class BeanServiceImpl implements BeanService {  
   private BeanDao beanDao;  
  
   @Override  
   public void test(){  
      beanDao.test();  
      System.out.println("BeanServiceImpl test....");  
   }  
  
   public void setBeanDao(BeanDao beanDao) {  
      this.beanDao = beanDao;  
   }  
}
```

4. Récupérer les Beans

```Java
public class Test1 {  
   @Test  
   public void test(){  
      ClassPathXmlApplicationContext classPathXmlApplicationContext 
	      = new ClassPathXmlApplicationContext("applicationContext.xml");  
  
      BeanService beanService = (BeanService) classPathXmlApplicationContext.getBean("beanService");  
      beanService.test();  
   }  
}
```

Normalement on récupère le bean par sa classe, tout en permettant à le récupérer par le nom de bean, mais il faut le définir tout d'abord.

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

Définir le bean dans applicationContext.xml

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

# Les méthodes de DI

## 1. Les manières différentes

1. Par setter
2. Par constructeur

## 2. Type de variable

1. Type primitif
2. Objet
3. Ficher .properties

# Par Annotation

1. Par applicationContext.xml

```java
<context:component-scan base-package="com.xxx.xxx" />
```

2. Par Class SpringConfig.java

```Java
@Configuration  
@ComponentScan("xxx")
@PropertySource("xxx")
```

3. Définir les beans

```Java

@Component("xxx")
	@Service("xxx")
	@Repository("xxx")  
	@Controller("xxx")

@Scope

@Autowired  
@Qualifier("xxx")

@Value("xxx")
@Value("${xxx}")

@PostConstruct
@PreDestroy

@import
```

4. Définir le bean tier

Créer un méthode qui renvoie le bean, puis ajouter annotation ```@Bean```

