
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
        http://www.springframework.org/schema/beans 
        http://www.springframework.org/schema/beans/spring-beans.xsd">  
  
    <!-- bean definitions here -->  
	<bean id="beanDao" class="com.xiaoyu.spring.dao.impl.BeanDaoImpl"/>  
	  
	<bean id="beanService" class="com.xiaoyu.spring.service.impl.BeanServiceImpl">  
	    <property name="beanDao" ref="beanDao"/>  
	</bean>
</beans>
```

3. Dans `beanService`, déclarer la variable `beanDao` et créer `setBeanDao`

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
