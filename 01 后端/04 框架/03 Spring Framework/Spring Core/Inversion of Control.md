#ioc 

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. Dans Spring, c'est par container IoC, il gère les objets comme des Beans, réalise **Dependency injection**, comme un relation entre les Beans

``` java
@Component("xxx")
	@Controller("xxx")
	@Service("xxx")
	@Repository("xxx")  

@Lazy
@Scope

@PostConstruct
@PreDestory

@Configuration
@Bean("beanId")
```

- `@Scope` a deux options `ConfigurableBeanFactory.SCOPE_SINGLETON` et `ConfigurableBeanFactory.SCOPE_PROTOTYPE`