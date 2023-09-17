#hibernate

Utiliser [[JDBC]] en base

Dans spring boot, l'implémentation de [[JPA]] par défaut est hibernate.

1. Ajouter les dépendances

``` xml
<dependency>  
    <groupId>com.mysql</groupId>  
    <artifactId>mysql-connector-j</artifactId>  
</dependency>  
<dependency>  
    <groupId>org.springframework.boot</groupId>  
    <artifactId>spring-boot-starter-data-jpa</artifactId>  
</dependency>
```

2. Définir les propriétés de `datasource`

``` properties
spring.datasource.url=jdbc:mysql://localhost:3306/student_tracker  
spring.datasource.username=springstudent  
spring.datasource.password=springstudent
```

3. Créer un `commandeLineRunner`

``` java
@Bean  
public CommandLineRunner commandLineRunner(String[] args){  
    return runner -> System.out.println("Hello world");  
}
```

4. Créer les entités

```java
@Entity  
@Table(name="Student")  
public class Student {  
    @Id  
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    @Column(name = "id")  
    private int id;  
    @Column(name = "first_name")  
    private String firstName;  
    @Column(name = "last_name")  
    private String lastName;  
    @Column(name = "email")  
    private String email;  
  
    public Student() {  
    }  
  
    public Student(String firstName, String lastName, String email) {  
       this.firstName = firstName;  
       this.lastName = lastName;  
       this.email = email;  
    }  

	// Getters and setters

    @Override  
    public String toString() {  
       return "Student{" +  
             "id=" + id +  
             ", firstName='" + firstName + '\'' +  
             ", lastName='" + lastName + '\'' +  
             ", email='" + email + '\'' +  
             '}';  
    }  
}
```

- Stratégie de génération par défaut:

```java
GenerationType.AUTO
GenerationType.INDENTITY
GenerationType.SEQUENCE
GenerationType.TABLE
```

- Stratégie de génération personnalisé: créer un implémentation de `org.hibernate.id.IdentifierGenerator`
- L'annotation `@Table` et `@Column` n'est pas obligé
- Le constructeur avec zéro-argument est obligé

> [!tip] 
> `@Transactional` annotation est pour démarrer et arrêter le transaction automatiquement
> 

