#ioc 

**Inversion of Control**, on crée un objet de l'extérieur de programme mais pas de l'intérieur par new. 

Dans Spring, c'est par container IoC, il gère les objets comme des [[Bean]], qui permet de réaliser [[Dependency injection]]

``` java

@Configuration
@Import

@[[Bean]]("[[Bean]]Id")
@[[Bean]](name = "", initMethod = "", destroyMethod = "", autowireCandidate = false)

@Component("xxx")
	@Controller("xxx")
	@Service("xxx")
	@Repository("xxx")

@Lazy(true)
@Scope("prototype")
@DependsOn("teacher")
```

- 通过注解生成的 [[Bean]] ，Spring 会默认生成这个 [[Bean]] 的 name，默认为类名驼峰首字母小写
