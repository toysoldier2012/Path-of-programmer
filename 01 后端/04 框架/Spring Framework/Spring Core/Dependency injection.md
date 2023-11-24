#di 

Créer un relation entre les [[Bean]].
有两种注入方式，通过 setter 注入和通过 constructor 注入

``` java
@Autowired
@Qualifier("beanId")

@Value("xxx")
@Value("${xxx}")
```

- `@Autowired` réalise DI par `byType` par défaut.
- 通过 `@Autowired` 自动装配，不需要写构造方法或 setter 方法
- 如果只有一个有参构造函数，可以不加 `@Autowired`