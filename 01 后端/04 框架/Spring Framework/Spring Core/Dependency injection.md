#di 

**Dependency injection**, c'est un relation entre les Beans

``` java
@Autowired
@Qualifier("beanId")

@Value("xxx")
@Value("${xxx}")
```

- `@Autowired` réalise DI par `byType
- `@Autowired` peut être sur paramètres, setter, constructeur, 形参
- 如果只有一个有参构造函数，可以不加 `@Autowired`