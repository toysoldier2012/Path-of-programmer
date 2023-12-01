
# QCM

### [Security] Authentication
Spring Security (40 pts)

Which of the following are possible approaches to accessing the currently logged-in user in a controller method?  

_Select all correct answers._ 

- Calling `SecurityContextHolder.getContext().getAuthentication()`
- Adding `Authentication authentication` as an argument to a controller method
- Adding `@Secured` to the method name
- Adding `@Authenticated` to the class definition

### [Data] Advantages of HQL
Spring Data (20 pts)

Which of the following are advantages of using Hibernate Query Language (HQL) over the native query dialect in a Spring Data repository?

- Shorter queries with the option to omit statements like `SELECT *` and specifying the `ON` portion of join statements
- Query validation on application startup
- Seamless migration to a different relational database dialect
- Interoperability between SQL and NoSQL databases

### [WebFlux] Flux type
Other (20 pts)

Spring WebFlux allows us to implement reactive programming.

Which core type, provided by WebFlux, should be used if a stream of responses needs to be returned to the client application instead of a single response?

- Stream
- Mono
- Flux
- Reactive

### [AOP] Aspect-Oriented Programming
Spring AOP (20 pts)

The software concept that encourages the separation of concerns by promoting reusable components in a Spring application is:

- Aspect-Oriented Programming
- Autowiring
- MVC Pattern
- eXtreme Programming

### [Core] Dependency Injection
Spring Core (20 pts)

What are the possible ways of accomplishing dependency injection using Spring?

_Select all correct answers._

- Constructor injection
- Setter injection
- Bean injection
- Interface injection

### [Jackson] @JsonIgnore
Other (40 pts)

Consider the following class that is to be used as a return type from a REST endpoint in a Spring Boot application:

```java
public class AccessLogData {
    private String userName;
    private Long timestamp;

    // getters and setters
}
```

And the following configuration of Jackson’s `ObjectMapper`:

```java
@Configuration
public class JsonConfig {
    @Bean
    public ObjectMapper configureJackson() {
        ObjectMapper mapper = new ObjectMapper();
        return mapper
    }
}
```

Suppose you would like to prevent null fields of `AccessLogData` from being serialized (without affecting the serialization of other classes). What should you do? 

- Add `@JsonInclude(JsonInclude.Include.NON_NULL)` as a class-level annotation to `AccessLogData`
- Add `mapper.setSerializationInclusion(Include.NON_NULL)` in `JsonConfig.configureJackson()`
- Add `@JsonIgnore` to the getters for `userName` and `timestamp` in `AccessLogData`
- Add `@JsonFilter(null)` as a class-level annotation to `AccessLogData`

### [AOP] Pointcut
Language knowledge (40 pts)

Which methods will be matched by this pointcut?  
  
![](https://static.codingame.com/work/servlet/fileservlet?id=18087718542321)  
  
_Multiple answers expected._

- public String findName()
- public char[] findPassword(boolean cache)
- protected String findAddress()
- public void createOrFindAccount(String name, char[] pass)

### [Core] Autowired constructor
Language knowledge (40 pts)

Which statement is correct about the `@Autowired(required=true)` annotation on constructors of a class?

- `@Autowired` can only be used on fields and setter methods
- `@Autowired` can be added on a constructor but it is not necessary
- `@Autowired` can be added on as many constructors as desired

### [Boot] @SpringBootTest
Spring Boot (20 pts)

What is the effect of adding the `@SpringBootTest` annotation to a test class?

- It is required to allow mock services for unit testing
- It sets up a complete application context for integration testing
- It allows application startup if a test case fails
- It starts a Spring Boot REPL for manual application probing

### [Core] Lazy
Language knowledge (40 pts)

A bean is annotated as `@Lazy`. When is it initialized?  
  
_Multiple answers expected._

- At Spring container startup
- When it is referenced by another bean
- When it is explicitly retrieved from the enclosing bean factory
- When it references another bean

### [Core] Application events
Language knowledge (40 pts)

Which application event does **NOT** exist in Spring Framework?

- ContextRefreshedEvent
- ContextStartedEvent
- ContextClosedEvent
- ContextLostEvent

### [Data] @ManyToOne(mappedBy = "user")
Spring Data (20 pts)

Consider the relationship between the two entities below:

```java
@Entity
public class User {
    @XXX
    private Address address;

    // getters and setters ...
}

@Entity
public class Address {
    @ManyToOne
    private User user

    // getters and setters ...
}
```

Which of the following annotations should replace `@XXX` and would result in the relationship being bidirectional?

- 
```java
@OneToMany(mappedBy = "user")
```

- 
```java
@OneToMany(useParentId = true)
```

- 
```java
@OneToMany(mappingRelationshipOwner = Address.class)
```

- 
```java
@OneToMany(mappingRelationshipOwner = User.class)
```

### [Boot] @SpringBootApplication
Spring Boot (20 pts)

Which of the following Spring Boot features is **not** enabled by default when an application is marked with `@SpringBootApplication`?

- Component scan
- Auto-configuration
- Dependency injection
- Scheduled tasks

### [Core] Injecting
Language knowledge (20 pts)

What annotation can you use to inject a Spring bean?

- @Autowired
- @PostConstruct
- @Bean
- @Component
- @InjectBean

### [Core] Singleton by default
Spring Core (20 pts)

By default, how many instances of a Spring bean would you find on the heap?

- One instance (singleton)
- One instance per class that specifies it as a dependency
- One instance per web request
- One instance per thread

### [Web] Request Lifecycle
Spring Web (20 pts)

When a request object leaves the client, its first stop when it enters into a Spring application is:

- ViewResolver
- DispatcherServlet
- Index JSP Page
- The first Spring Controller it can find

### Parmi les affirmations suivantes sur l'attribut fetch (JPA), lesquelles sont fausses? 

- Cet attribut peut prendre deux valeurs: FetchType. LAZY et FetchType. EAGER
- Pas de règle générale pour l'utilisation de cet attribut. Chaque cas est un cas particulier, qu'il faut traiter en tant que tel!
- La valeur FetchType. EAGER indique que la relation doit être chargée à la demande
- Défini uniquement sur l'annotation @OneToMany

### Quel est le scope (mode d'instanciation) par défaut pour les beans spring? Une seule réponse acceptée. 
- prototype
- singleton
- session
- request
- application

# Text

# Code







































