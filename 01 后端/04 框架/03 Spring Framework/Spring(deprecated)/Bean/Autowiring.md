#autowire

# Dans les balises `bean` avec `autowire`

- `no/default`
- `byType`
- `byName`
- `constructor`

```xml
<bean class="com.xiaoyu.spring.controller.UserController" autowire="byType"/>  
<bean class="com.xiaoyu.spring.service.impl.UserServiceImpl" autowire="byType"/>  
<bean class="com.xiaoyu.spring.dao.impl.UserDaoImpl"/>
```

# Par Annotation

## 1. Scanner

### Par ficher .xml

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

### Par ficher .java

```Java
@Configuration  
@ComponentScan("xxx")
@PropertySource("xxx")
```

```java
ApplicationContext context = new AnnotationConfigApplicationContext(SpringConfig.java);
```

## 2. Les annotations

### Pour IoC

``` java
@Component("xxx")
	@Controller("xxx")
	@Service("xxx")
	@Repository("xxx")  

@Lazy
@Scope
```

- `@Scope` a deux options `ConfigurableBeanFactory.SCOPE_SINGLETON` et `ConfigurableBeanFactory.SCOPE_PROTOTYPE`
### Pour DI

``` java
@Autowired
@Qualifier("xxx")

@Value("xxx")
@Value("${xxx}")
```

- `@Autowired` réalise DI par `byType
- `@Autowired` peut être sur paramètres, setter, constructeur, 形参
- 如果只有一个有参构造函数，可以不加 `@Autowired`

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
