
# QCM

### persist() with a bidirectional one-to-many relationship
Relationship (40 pts)

Given the following entities, what will be the result of the code written below?

`Product` class:

```java
@Entity
public class Product {
    @Id
    @GeneratedValue(strategie = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private int cost;
    @OneToMany(mappedBy = "product", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<Comment> comments;
}
```

`Comment` class:

```java
@Entity
public class Comment {
    @Id
    @GeneratedValue(strategie = GenerationType.IDENTITY)
    private Long id;
    private String content;
    @ManyToOne
    @JoinColumn(name = "product_id")
    private Product product;
}
```

Executed code:

```java
Product product = new Product("myProduct", 10);
Comment comment1 = new Comment("first comment");
Comment comment2 = new Comment("second comment");

product.getComments().add(comment1);
comment1.setProduct(product);
product.getComments().add(comment2);
comment2.setProduct(product);

entityManager.persist(product);
```

- The product will be inserted in the database but not the comments
- The product and comments will be inserted in the database but the foreign key column will be empty
- The product and the comments will be inserted in the database without any malfunction
- The `persist()` statement will fail with an SQL error

### Batch mode - Operation delete
Batching (40 pts)

Given that the `hibernate.jdbc.batch_size` property contains the value **10**, how many SQL queries will be executed as a result of the code below?

```java
List<User> users = entityManager.createQuery("select u from User u ", User.class).getResultList();

for(User user : users) {
    entityManager.remove(user);
}
```

The code of the `User` class is as follows:

```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private Integer id;
    private String name;

    public User(String name, Integer id) {
        this.id = id;
        this.name = name;
    }
}
```

- 10
- 5
- 1
- 0

### Eager fetching
Lazy vs eager (40 pts)

Consider the following two Hibernate entities:

```java
@Entity
public class Company {
	@Id
	private Long id;
	@ManyToMany
	private Collection<Employee> employees;

	// ...
}​
```

```java
@Entity
public class Employee {
	private String name;

	// ...
}
```

And the following repository:

```java
@Repository
public interface CompanyRepository extends JpaRepository<Company, Long> {
	private Company findByIdFetchingEmployeesEagerly(Long id);
}
```

Suppose that the developer wishes to eagerly fetch both the `Company` and any child `Employee` classes when (and only when) `findByIdFetchingEmployeesEagerly` is called.

Which of the following strategies would accomplish this goal?

- Adding `(fetch = FetchType.EAGER)` to the existing `@ManyToMany` annotation on the `employees` field of `Company`
- Adding `(fetch = FetchType.LAZY)` to the existing `@ManyToMany` annotation on the `employees` field of `Company`
- Annotating `findByIdFetchingEmployeesEagerly` with a HQL `@Query` that specifies to `join fetch` employees
- Annotating `findByIdFetchingEmployeesEagerly` with `@Eager(entity = Employees.class)`

### Join table with an additional column
Relationship (40 pts)

How do you implement an entity schema that allows you to manage a join table with an additional column?

- The `@ManyToMany` relationship allows to manage it thanks to the `ExtraColumn` property
- A new entity must be created to represent the join table and `@OneToMany` and `@ManyToOne` relationships must be used
- New methods must be added to the entities that define the `@ManyToMany` annotation
- You must use the `@ElementCollection` annotation

### LazyInitializationException
Lazy vs eager (40 pts)

What could be the cause of the following exception?

```text
org.hibernate.LazyInitializationException : could not initialize proxy – no Session.
```

- Accessing an entity through a reference from a related entity after the session that retrieved that related entity has been closed
- Attempting to commit multiple update statements within a single transaction without flushing
- Failing to include on the classpath an appropriate connector jar for the database implementation being used
- Retrieving an entity by ID without an active Hibernate session

### @PreUpdate
Entity (40 pts)

When does Hibernate invoke an entity method annotated with `@PreUpdate`? 

- Only before the first time an entity is saved
- Only on subsequent saves to an entity that has been saved at least once
- Only when a timestamp field has been changed
- Only when an id field (annotated with `@Id`) has been changed

### Connection provider
Other concepts (40 pts)

Which of the following connection providers are commonly used with Hibernate?

- `CP3P0ConnectionProvider`
- `HikariCPConnectionProvider`
- `DatasourceConnectionProvider`
- `JdbcConnectionProvider`

### Default behavior of a one-to-many relationship
Relationship (20 pts)

What will be the result of the following entities in the database with the unidirectional relationship `@OneToMany`?

Class `Product`:

```java
@Entity
public class Product {
    
    @Id
    @GeneratedValue
    private Long id;
    private String name;
    @OneToMany(cascade = CascadeType.ALL, orphanRemoval = true)
    private List<Comment> comment;

}
```

Class `Comment`:

```java
@Entity
public class Comment {
    @Id
    @GeneratedValue
    private Long id;
    private String content;
}
```

- 
```sql
    CREATE TABLE product (
        id BIGINT(20) PRIMARY_KEY,
        name VARCHAR(255)
    )
    
    CREATE TABLE comment (
        id BIGINT(20) PRIMARY_KEY,
        content VARCHAR(255),
        product_id BIGINT(20)
    )
    ```
    
- 
```sql
    CREATE TABLE product (
        id BIGINT(20) PRIMARY_KEY,
        name VARCHAR(255)
    )
    
    CREATE TABLE product_comment (
        product_id BIGINT(20) PRIMARY_KEY,
        comment_id BIGINT(20) PRIMARY_KEY
    )
    
    CREATE TABLE comment (
        id BIGINT(20) PRIMARY_KEY,
        content VARCHAR(255)
    )
    ```
    
- 
```sql
    CREATE TABLE product (
        id BIGINT(20) PRIMARY_KEY,
        name VARCHAR(255)
    )
    
    CREATE TABLE comment (
        id BIGINT(20) PRIMARY_KEY,
        content VARCHAR(255)
    )
    ```

### @GeneratedValue
Entity (20 pts)

Which of the following standard Java annotations would replace `@XXX` to instruct Hibernate to automatically generate and assign a sequential value to `id` before saving the entity (if `id` is null)?

```java
@Entity
class User {

	@Id
	@XXX
	private Long id;

	public Long getId() {
		return this.id;
	}
}​
```

- `@GeneratedValue`
- `@AutoIncrement`
- `@Sequential`
- `@Order`

### Default cascade behavior on a relationship
Relationship (20 pts)

Within a relation `@OneToOne`, `@OneToMany`, `@ManyToOne` or `@ManyToMany`, what is the default value if the `cascade` property is not defined?

- `CascadeType.MERGE`
- `CascadeType.PERSIST`
- `CascadeType.REMOVE`
- `CascadeType.ALL`
- No `CascadeType` is defined

### JDBC vs JPA - Resolving relationships
Persistence (20 pts)

What is the difference between JDBC and JPA when it comes to resolving relationships (i.e. transforming the relationship into an object)?

- JPA reuses the JDBC mechanism so there are no differences
    
- -JDBC transforms the relationship into an object implicitly  
   -JPA requires you to write the logic for transforming the relationship into an object
    
- -JPA implicitly transforms the relationship into an object based on the structure of the defined entities  
   -JDBC requires a manual transformation of relationships into objects

### Many-to-many relationship and cascade type
Relationship (20 pts)

An entity named `User` has a unidirectional many-to-many relationship to an entity `Role`. The deletion of a user should not result in the deletion of any associated roles.

Which cascade types should **not** be used?

- `CascadeType.PERSIST`
- `CascadeType.MERGE`
- `CascadeType.REMOVE`
- `CascadeType.ALL`

### One-to-many relationship @OneToMany
Relationship (20 pts)

Which annotation expresses a one-to-many relationship (on the parent-side) between 2 entities?

- `@OneToMany`
- `@ManyToOne`
- `@ElementCollection`
- `@ManyToMany`

### JPA vs Hibernate
Persistence (20 pts)

What is the difference between JPA and Hibernate?

- There are no differences, they are both specifications for managing data persistence
- JPA is a specification and Hibernate is an implementation for data persistence
- Hibernate is a specification and JPA is an implementation for data persistence
- There are no differences, they are both implementations for data persistence

# Text

### Number of tables

Consider the following two Hibernate entities:

```java
@Entity
public class Vehicle {
    @Id
    private Long id;
    
    @ManyToMany
    private List<Driver> drivers;

    // getters and setters
}
```

```java
@Entity
public class Driver {
    @Id
    private Long id;
    
    @ManyToMany
    private List<Vehicle> vehiclesDriven;

    // getters and setters
}
```

How many tables would you expect Hibernate to generate for these two entities when used with a relational database?

_Answer with a number._


# Code
