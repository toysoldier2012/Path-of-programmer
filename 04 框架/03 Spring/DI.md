
**Dependency injection**, comme un relation entre les Beans

# Les manières différentes

## 1. Par setter

``` xml
<bean id="actor" class="com.xiaoyu.spring.pojo.Actor">  
    <property name="id" value="1"/>  
    <property name="name" value="xiaoyu"/>  
    <property name="gender" value="m"/>  
</bean>
```

## 2. Par constructeur

``` xml
<bean id="actor" class="com.xiaoyu.spring.pojo.Actor">  
    <constructor-arg name="id" value="1002"></constructor-arg>  
    <constructor-arg name="name" value="yezi"></constructor-arg>  
    <constructor-arg name="gender" value="f"></constructor-arg>  
</bean>
```

# Type de variable

## 1. Type primitif

## 2. null

``` xml
<property name="name" value="xiaoyu">  
    <null/>
</property>
```

## 3. 复杂字符

``` xml
<property name="gender">  
    <value><![CDATA[a < b]]></value>  
</property>
```

## 4. Objet

``` xml
<property name="film" ref="film"/>

<property name="film" ref="filmA"/>  
<property name="film.id" value="123"></property>  
<property name="film.name" value="asdf"></property>

<property name="film">  
    <bean id="filmB" class="com.xiaoyu.spring.pojo.Film">  
        <property name="id" value="123"></property>  
        <property name="name" value="asdf"></property>  
    </bean>
</property>
```

第三种方法中定义的内部Bean，只能在Bean内部使用

## 5. Array

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

## 6. Collection

``` xml
<property name="helloSprings">  
    <list>        
	    <ref bean="helloSpring"></ref>  
        <ref bean="helloSpring"></ref>  
        <ref bean="helloSpring"></ref>  
    </list>
</property>
```



## 5. Ficher `.properties`

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
