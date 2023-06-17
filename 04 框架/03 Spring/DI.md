
**Dependency injection**, comme un relation entre les Beans

# Dans `applicationContext.xml`

##  1. Les manières

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

## 2. Type de variable

### Type primitif

### null

``` xml
<property name="name" value="xiaoyu">  
    <null/>
</property>
```

### 复杂字符

``` xml
<property name="gender">  
    <value><![CDATA[a < b]]></value>  
</property>
```

### Objet

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

### Array

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

### List

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

### Map

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

### `.properties`文件

``` xml
<?xml version="1.0" encoding="UTF-8"?>  
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       
       xmlns:context="http://www.springframework.org/schema/context"  
       
       xsi:schemaLocation="  
		http://www.springframework.org/schema/beans        
		http://www.springframework.org/schema/beans/spring-beans.xsd        
		
		http://www.springframework.org/schema/context        
		http://www.springframework.org/schema/context/spring-context.xsd">  
  
    <context:property-placeholder location="jdbc.properties"/>  
  
    <bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource">  
        <property name="driverClassName" value="${jdbc.sakila.driver}"/>  
        <property name="url" value="${jdbc.sakila.url}"/>  
        <property name="username" value="${jdbc.sakila.username}"/>  
        <property name="password" value="${jdbc.sakila.password}"/>  
    </bean>
</beans>
```

# Autowiring

## 1. Dans les balises bean par `autowire`

- `no/default`
- `byType`
- `byName`
- `constructor`

```xml
<bean class="com.xiaoyu.spring.controller.UserController" autowire="byType"/>  
<bean class="com.xiaoyu.spring.service.impl.UserServiceImpl" autowire="byType"/>  
<bean class="com.xiaoyu.spring.dao.impl.UserDaoImpl"/>
```

## 2. Par Annotation

### Scanner

#### Dans .xml

1. Analyser les composants

```xml
<?xml version="1.0" encoding="UTF-8"?>  
<beans xmlns="http://www.springframework.org/schema/beans"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
       xmlns:context="http://www.springframework.org/schema/context"  
       xsi:schemaLocation="  
		http://www.springframework.org/schema/beans        
		http://www.springframework.org/schema/beans/spring-beans.xsd        
		http://www.springframework.org/schema/context        
		http://www.springframework.org/schema/context/spring-context.xsd">  
  
        <context:component-scan base-package="com.xiaoyu.spring" />  
</beans>
```

- Filtre d'exclusion

``` xml
<context:component-scan base-package="com.xiaoyu.spring">
	<context:exclude-filter type="annotation" expression="org.springframework.stereotype.Controller"/>  
</context:component-scan>
```

- Filtre d'inclusion, nécessité d'ajouter la paramètre `use-default-filters`

``` xml
<context:component-scan base-package="com.xiaoyu.spring" use-default-filters="false">  
	<context:include-filter type="annotation" expression="org.springframework.stereotype.Controller"/>  
</context:component-scan>
```

#### Par ficher SpringConfig.java

```Java
@Configuration  
@ComponentScan("xxx")
@PropertySource("xxx")
```

```java
ApplicationContext context = 
	new AnnotationConfigApplicationContext(SpringConfig.java);
```

### Définir les beans

#### Pour IoC

``` java
@Component("xxx")
	@Controller("xxx")
	@Service("xxx")
	@Repository("xxx")  
	
@Scope
```

#### Pour DI

``` java
@Autowired
@Qualifier("xxx")

@Value("xxx")
@Value("${xxx}")
```

- `@Autowired` réalise DI par `byType
- `@Autowired` peut être sur paramètres, setter, constructeur, 形参
- 如果只有一个有参构造函数，可以不加 `@Autowired`
- `@Qualifier` utilise l'ID d'un Bean spécifique pour DI dans le Bean actuel

```java
@Reasouce
@Reasouce(name="")
```

- 默认 byName 注入
- 没有指定“name”时，将属性名当成 name
- byName 找不到时，切换为 byType，此时同类型 Bean 只能有一个

> [!todo] 
> @PostConstruct
@PreDestroy
@import 
>```@Bean```
>- Définir le bean tier
Créer un méthode qui renvoie le bean, puis ajouter annotation 

