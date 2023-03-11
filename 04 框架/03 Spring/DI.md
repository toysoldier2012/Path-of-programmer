
**Dependency injection**, comme un relation entre les Beans

# Dans `applicationContext.xml`

## 1. Par les balises `bean`

### Manières

``` xml
<!-- setter -->

<bean id="actor" class="com.xiaoyu.spring.pojo.Actor">  
    <property name="id" value="1"/>  
    <property name="name" value="xiaoyu"/>  
    <property name="gender" value="m"/>  
</bean>

<!-- constructeur -->

<bean id="actor" class="com.xiaoyu.spring.pojo.Actor">  
    <constructor-arg name="id" value="1002"></constructor-arg>  
    <constructor-arg name="name" value="yezi"></constructor-arg>  
    <constructor-arg name="gender" value="f"></constructor-arg>  
</bean>

<!-- p:namespace -->

<bean id="actorB" class="com.xiaoyu.spring.pojo.Actor" 
	  p:id="100" 
	  p:name="abcdeft" 
	  p:film-ref="filmC" 
	  p:gender="M"  
      p:helloSprings-ref="helloSprings" 
      p:testMaps-ref="testMapsB"
/>
```

### Type de variable

#### 1. Type primitif

#### 2. null

``` xml
<property name="name" value="xiaoyu">  
    <null/>
</property>
```

#### 3. 复杂字符

``` xml
<property name="gender">  
    <value><![CDATA[a < b]]></value>  
</property>
```

#### 4. Objet

``` xml
<!-- 普通方式 -->

<property name="film" ref="film"/>

<!-- 级联方式 -->

<property name="film" ref="filmA"/>  
<property name="film.id" value="123"></property>  
<property name="film.name" value="asdf"></property>

<!-- 内部bean方式，定义的bean，只能在bean内部使用 -->

<property name="film">  
    <bean id="filmB" class="com.xiaoyu.spring.pojo.Film">  
        <property name="id" value="123"></property>  
        <property name="name" value="asdf"></property>  
    </bean>
</property>
```

#### 5. Array

``` xml
<property name="hobby">  
	<array>
		<value>a</value>  
		<value>b</value>  
		<value>c</value>
		<!--<ref></ref>-->
		<!--<ref></ref>-->
	</array>
</property>
```

#### 6. List

- 通过`list`标签配置

``` xml
<property name="helloSprings">  
    <list>        
	    <ref bean="helloSpring"></ref>  
        <ref bean="helloSpring"></ref>  
        <ref bean="helloSpring"></ref>  
    </list>
</property>
```

- 通过`util:list`标签

Ajouter les balises `util:` dans [[IoC#^e4c41f|namespace]]

```xml
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       
       xmlns:util="http://www.springframework.org/schema/util"
       
       xsi:schemaLocation="
		http://www.springframework.org/schema/beans
		http://www.springframework.org/schema/beans/spring-beans.xsd
		
		http://www.springframework.org/schema/util
		http://www.springframework.org/schema/util/spring-util-4.0.xsd">
```

``` xml
<property name="helloSprings" ref="helloSprings"></property>

<util:list id="helloSprings">  
    <ref bean="helloSpring"></ref>  
    <ref bean="helloSpring"></ref>  
    <ref bean="helloSpring"></ref>  
</util:list>
```

#### 7. Map

``` xml
<property name="testMaps">  
    <map>
        <entry key="a" value-ref="filmC"></entry>  
        <entry key="b" value-ref="filmC"></entry>  
        <entry key="c" value-ref="filmC"></entry>  
    </map>
</property>

<bean id="filmC" class="com.xiaoyu.spring.pojo.Film">  
    <property name="id" value="1"/>  
    <property name="name" value="b"/>  
</bean>
```

Dans les balises `entry`, on a 5 paramètres:
- `key`
- `key-ref`
- `value`
- `value-ref`
- `value-type`

#### 8. `.properties`文件

``` xml
<?xml version="1.0" encoding="UTF-8"?>  
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       
       xmlns:context="http://www.springframework.org/schema/context"  
       
       xsi:schemaLocation="  
		http://www.springframework.org/schema/beans        
		http://www.springframework.org/schema/beans/spring-beans.xsd        
		
		http://www.springframework.org/schema/context        
		http://www.springframework.org/schema/context/spring-context-4.2.xsd">  
  
    <context:property-placeholder location="jdbc.properties"/>  
  
    <bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource">  
        <property name="driverClassName" value="${jdbc.sakila.driver}"/>  
        <property name="url" value="${jdbc.sakila.url}"/>  
        <property name="username" value="${jdbc.sakila.username}"/>  
        <property name="password" value="${jdbc.sakila.password}"/>  
    </bean>
</beans>
```


## 2. Par Annotation

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
