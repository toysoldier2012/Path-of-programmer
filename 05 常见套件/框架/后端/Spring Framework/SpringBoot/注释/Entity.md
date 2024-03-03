
``` java
@Entity
public class Student {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;

    @ManyToMany
    @JoinTable(
      name = "student_course", 
      joinColumns = @JoinColumn(name = "student_id"), 
      inverseJoinColumns = @JoinColumn(name = "course_id"))
    private Set<Course> courses = new HashSet<>();

    // getters and setters
}

@Entity
public class Course {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;

    @ManyToMany(mappedBy = "courses")
    private Set<Student> students = new HashSet<>();

    // getters and setters
}
```

^b12b6e

# @GeneratedValue

`@GeneratedValue` 是 JPA（Java Persistence API）中的一个注解，用于在持久化过程中生成实体的主键值。当你保存一个新的实体到数据库时，JPA 会根据你的 `@GeneratedValue` 配置来决定主键的生成策略。

`@GeneratedValue` 注解通常与 `@Id` 注解一起使用来标注实体的主键字段或属性，`@Id` 用于声明一个字段是实体的主键。

下面是一个简单的使用例子：

```java
@Entity
public class Book {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String title;
    private String author;

    // getters and setters
}
```

在这个示例中，`id` 字段是实体的主键，并通过 `@GeneratedValue` 标记为自动生成的。`strategy` 属性定义了主键的生成策略。常见的生成策略包括：

## 1. `GenerationType.AUTO` (默认)

JPA 提供商（如 Hibernate）将选择最合适的策略，基于具体的数据库的能力。在某些数据库中，这可能意味着使用序列；在其他数据库中，这可能意味着使用标识或者表生成器。

## 2. `GenerationType.IDENTITY`

这个策略通常用在 SQL 数据库中，它依赖于数据库表的自增字段。也就是说，数据库将自动为每一条新记录分配一个新的主键值。这是一种在像 MySQL 这样的数据库中常见的策略。

## 3. `GenerationType.SEQUENCE`

这个策略用于数据库中的序列来生成主键。序列是一个由数据库管理的唯一值生成器。你可以定义序列的名称，以及预分配大小等。这个策略常用于像 PostgreSQL、Oracle 这样的数据库。

```java
@Id
@GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "book_generator")
@SequenceGenerator(name="book_generator", sequenceName = "book_seq", allocationSize=1)
private Long id;
```

在上述代码中：

- `generator`: 指定生成器的名称。
- `sequenceName`: 指定数据库中的序列名。
- `allocationSize`: 指定序列的增量。

## 4. `GenerationType.TABLE`

这种策略通过使用特定的数据库表来模拟序列，并生成唯一的主键值。这是一种比较便携的策略，因为它在所有支持表的数据库中都可以工作，但可能不如其他策略那么高效。

使用 `@GeneratedValue` 注解的主要目的是允许数据库在插入新记录时自动处理主键的生成，从而减轻开发人员的负担，并减少错误的可能性。不同的生成策略在不同的数据库和应用场景中有着各自的优缺点，通常需要根据实际需求进行选择。

# @JoinTable

`@JoinTable` 是 JPA (Java Persistence API) 中的一个注解，通常用在实体类的属性上，用于定义实体之间的关系映射。更具体地说，`@JoinTable` 通常用于定义多对多 (`@ManyToMany`) 和一对多 (`@OneToMany`) 关系的连接表的细节。

## 基本用法

在多对多关系中，`@JoinTable` 常用于指定由两个实体关联的中间表。该中间表通常包含两个外键列，分别引用关联的两个实体表。

下面是一个使用 `@JoinTable` 的基本示例。这里有两个实体类：`Student` 和 `Course`，它们之间存在多对多关系，关系的映射细节由 `@JoinTable` 定义。

在 [[Entity#^b12b6e|开始]] 的代码中：

- `@JoinTable` 注解用于 `Student` 实体的 `courses` 属性上。
    
- `name`: 指定连接表（中间表）的名字。在这个例子中，连接表的名字是 "student_course"。
    
- `joinColumns`: 指定本实体（`Student`）在连接表中的外键列的细节。这里，连接表 "student_course" 包含一个名为 "student_id" 的外键列，该列引用 "student" 表的主键列。
    
- `inverseJoinColumns`: 指定目标实体（`Course`）在连接表中的外键列的细节。这里，连接表 "student_course" 包含一个名为 "course_id" 的外键列，该列引用 "course" 表的主键列。
    
## 注意点

- 当你使用 `@JoinTable` 时，你实际上是在 DB 中创建了一个新表，用于维护实体之间的关系。这个表主要包含两个外键列，分别引用关联的两个实体表的主键列。
    
- `mappedBy` 属性表示该实体是关系的非拥有方。在上面的例子中，`Course` 实体的 `students` 属性使用 `mappedBy` 指定了 `Student` 实体的 `courses` 属性为关系的拥有方。

# @ManyToMany

在 JPA（Java Persistence API）中，`@ManyToMany` 是一个常见的注解，用于表示两个实体之间的双向关系，而且每一方都可以关联对方的多个实例。为了维护 `@ManyToMany` 关系，JPA 通常使用一个关联表（也称为联接表或映射表）来跟踪两个实体之间的关系。

## 基本用法

在 [[Entity#^b12b6e|开始]] 的例子中：

- `@JoinTable`: 它定义了两个实体之间的关联表。
    - `name`: 关联表的名称。
    - `joinColumns`: `Student` 实体在关联表中的外键。
    - `inverseJoinColumns`: `Course` 实体在关联表中的外键。
- `mappedBy`: 它定义了实体关系的“非拥有”一方。在这个例子中，"courses"是`Student`实体中`Set<Course>`的字段名。

## 考虑的问题

### 1. 懒加载 vs 饿加载

你可以使用 `fetch` 属性来设置关系的加载类型：

- `FetchType.LAZY`（懒加载）: 关系将在首次访问时被加载，而不是在获取父实体时立即加载。

```java
@ManyToMany(fetch = FetchType.LAZY)
```

- `FetchType.EAGER`（饿加载）: 关系将立即与父实体一起被加载。

```java
@ManyToMany(fetch = FetchType.EAGER)
```

### 2. 级联操作

你可以使用 `cascade` 属性来设置级联操作的类型：

- `CascadeType.ALL`: 所有实体操作都将被级联。
- `CascadeType.PERSIST`: 保存父实体时也会保存关系。
- `CascadeType.MERGE`: 合并父实体时也会合并关系。

```java
@ManyToMany(cascade = CascadeType.ALL)
```

### 3. 解决循环依赖的问题

正如在前面的对话中所讨论的，你需要使用某种方法来处理/防止实体在被序列化时出现的循环依赖问题。你可以使用 `@JsonManagedReference`、`@JsonBackReference` 或 `@JsonIdentityInfo` 等注解。

## 使用注意

- 在处理`@ManyToMany`关系时，你需要确保正确地更新关系的两侧以保持它们的同步。
- `@ManyToMany`关系可能会使事务变得复杂，尤其是在大规模数据集上。永远要注意性能问题，并在可能的情况下选择使用`FetchType.LAZY`来优化数据加载。

确保理解并合理使用`@ManyToMany`关系，为您的特定用例选择最适当的配置和策略。

# @ManyToOne 

- **多对一 (`@ManyToOne`)**：多个实体关联到一个实体。例如，在一个“文章（`Post`）和作者（`Author`）”的关系中，多个文章可能由一个作者编写，所以在 `Post` 实体中我们可能定义一个 `@ManyToOne` 的关系到 `Author`。

## 基本用法

在使用 `@ManyToOne` 注解时，你通常会在“多”的那一方的实体中使用它，指向“一”的那一方的实体。例如：

```java
@Entity
public class Post {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String title;
    private String content;

    @ManyToOne
    @JoinColumn(name = "author_id")
    private Author author;

    // getters and setters
}

@Entity
public class Author {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;

    @OneToMany(mappedBy = "author")
    private List<Post> posts;

    // getters and setters
}
```

在这个例子中：

- `Post` 实体包含一个 `author` 属性，表示一个文章的作者。这里使用了 `@ManyToOne` 注解，表示一个作者可以写多篇文章，但一篇文章只能由一个作者编写。
    
- `@JoinColumn` 注解用于指定外键列的信息。在这个例子中，"author_id" 列是 `Post` 表中的外键列，它引用了 `Author` 表的主键列。
    
- 在 `Author` 实体中，我们用 `@OneToMany` 定义了反向的关系，并使用 `mappedBy` 属性指明 `Post` 实体中的 `author` 属性是这一关系的拥有方。

# @OneToOne

假设我们有两个实体类：`User` 和 `UserProfile`，我们希望这两个实体之间有一个一对一的关系。可以这样定义：

```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String username;

    @OneToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "profile_id", referencedColumnName = "id")
    private UserProfile profile;

    // getters and setters
}

@Entity
public class UserProfile {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String firstName;
    private String lastName;

    @OneToOne(mappedBy = "profile")
    private User user;

    // getters and setters
}
```

在上述代码中：

- `User` 实体中的 `@OneToOne` 注解定义了与 `UserProfile` 实体的一对一关系。
    
- `cascade = CascadeType.ALL` 表示这个关系是级联的。这意味着如果我们保存/更新/删除一个 `User` 对象，那么关联的 `UserProfile` 也将相应地被保存/更新/删除。
    
- `@JoinColumn(name = "profile_id", referencedColumnName = "id")` 表示在 `User` 表中创建一个名为 `profile_id` 的外键列，该列引用 `UserProfile` 表的 `id` 列。
    
- 在 `UserProfile` 实体中，`mappedBy = "profile"` 属性指定了 `User` 实体中的 `profile` 属性是这个一对一关系的拥有方。这样，`UserProfile` 表中不会创建额外的外键列。
    
## 注意点

- `mappedBy`：这个属性定义了关系的拥有方。在上述例子中，`UserProfile` 通过 `mappedBy` 属性标记为非拥有方。这意味着任何对关系的改变都应该通过 `User` 实体来进行。
    
- `@JoinColumn`：这个注解通常在一对一关系的拥有方上使用，用于定义外键列的细节。
    
- 一对一关系通常需要仔细设计数据模型，以确保这样的关系真正适用于你的用例，因为在某些情况下，它们可能导致性能问题（例如：不必要的 JOIN 操作）。

# @JsonManagedReference 和 @JsonBackReference

```java
@Entity
public class Pet {
    //... 其他字段

    @ManyToOne
    @JoinColumn(name = "owner_id")
    @JsonBackReference
    private Owner owner;
    
    // getters and setters
}

@Entity
public class Owner {
    //... 其他字段
    
    @OneToMany(mappedBy = "owner")
    @JsonManagedReference
    private List<Pet> pets;
    
    // getters and setters
}

```

当你尝试序列化一个 `Pet` 实体时，它将尝试序列化 `Owner` 字段，然后对于每个 `Owner` 实体，它又会尝试序列化它的 `pets` 列表，以此类推，形成一个无限循环。

为了解决这个问题，你可以使用 `@JsonManagedReference` 和 `@JsonBackReference` 注解

# @JsonIdentityInfo

`@JsonIdentityInfo` 是 Jackson 库中的一个注解，用于处理 JSON 序列化和反序列化过程中的循环引用问题。在实体关系中，如果两个或多个对象相互引用，并且你试图将它们序列化为 JSON，则会导致无限循环和 `StackOverflowError`。`@JsonIdentityInfo` 通过在生成的 JSON 中引入一个 ID 来避免这个问题，这样，当对象再次被引用时，Jackson 只序列化对象的 ID，而不是整个对象。

## 示例

让我们通过一个简单的示例来看看 `@JsonIdentityInfo` 的实际应用。

假设你有两个相互引用的实体类：`Person` 和 `Car`。

```java
@JsonIdentityInfo(
    generator = ObjectIdGenerators.PropertyGenerator.class, 
    property  = "id"
)
public class Person {
    private Long id;
    private String name;
    private Car car;
    // getters and setters
}

@JsonIdentityInfo(
    generator = ObjectIdGenerators.PropertyGenerator.class, 
    property  = "id"
)
public class Car {
    private Long id;
    private String model;
    private Person owner;
    // getters and setters
}
```

- `generator`: 定义了 ID 的生成策略。常用的生成器有 `PropertyGenerator`（使用实体的一个属性作为 ID）和 `IntSequenceGenerator`（使用一个整数序列作为 ID）。
- `property`: 如果你使用 `PropertyGenerator`，你需要通过 `property` 属性指定哪个实体属性应该用作 ID。

在这个例子中，每个 `Person` 对象都引用一个 `Car` 对象，并且每个 `Car` 对象都反过来引用一个 `Person` 对象。如果没有 `@JsonIdentityInfo`，当你尝试将一个 `Person` 或 `Car` 对象序列化为 JSON 时，你会得到一个 `StackOverflowError`，因为 Jackson 会不断在两个对象之间来回跳转。通过使用 `@JsonIdentityInfo`，Jackson 将只序列化每个对象一次，并在后续的引用中只序列化其 ID。

### 示例输出

假设你尝试序列化一个 `Person` 对象，其 `Car` 对象也引用该 `Person` 对象。不使用 `@JsonIdentityInfo`，序列化将无限循环。使用 `@JsonIdentityInfo`，输出的 JSON 可能看起来像这样：

```java
{
    "id": 1,
    "name": "John",
    "car": {
        "id": 123,
        "model": "Toyota",
        "owner": 1
    }
}
```

请注意 `owner` 字段只包含一个 ID 值而不是整个 `Person` 对象。这就是 `@JsonIdentityInfo` 避免无限循环的方式。

## 使用注意

- 如果你使用 Spring Data REST 或某些其他框架，可能需要其他或附加的配置来确保 `@JsonIdentityInfo` 正常工作。
- 在前端，你需要确保你的代码能够理解和处理这种形式的 JSON，可能需要额外的逻辑来根据 ID 重新构建对象引用。

# @JsonView

`@JsonView` 是 Jackson 库中的一个注解，它允许你定义 JSON 序列化过程中的视图，从而能够定制你想要输出的 JSON 结构。通过使用视图，你可以控制哪些属性应该在特定的序列化场景中被包括，从而提供一种方法来灵活地控制你的 JSON 输出。

## 基本概念

### 定义视图

视图本质上只是一个或多个标记接口，它们不包含任何方法。例如：

```java
public class Views {
    public static class Public {}
    public static class Internal extends Public {}
}
```

在这个例子中，我们定义了两个视图：`Public` 和 `Internal`。`Internal` 视图继承自 `Public` 视图，意味着任何标记为 `Public` 视图的属性也会被包括在 `Internal` 视图中。

### 使用视图

使用定义的视图来标记你的模型类的属性：

```java
public class Item {
    @JsonView(Views.Public.class)
    public int id;
    
    @JsonView(Views.Public.class)
    public String itemName;
    
    @JsonView(Views.Internal.class)
    public String ownerName;
}
```

在这个例子中，`id` 和 `itemName` 属性将会在 `Public` 视图中被序列化，而 `ownerName` 属性只会在 `Internal` 视图中被序列化。

### 使用 `@JsonView` 进行序列化

在序列化过程中使用视图：

```java
ObjectMapper mapper = new ObjectMapper();
Item item = new Item();
// fill item data

// Serialize using the public view
String publicViewJson = mapper
        .writerWithView(Views.Public.class)
        .writeValueAsString(item);
        
// Serialize using the internal view
String internalViewJson = mapper
        .writerWithView(Views.Internal.class)
        .writeValueAsString(item);
```

在第一个例子中，`publicViewJson` 只包含 `id` 和 `itemName` 属性。在第二个例子中，`internalViewJson` 包含 `id`、`itemName` 和 `ownerName` 属性。

### 在 Spring MVC 中使用 `@JsonView`

如果你使用 Spring MVC，你可以在你的控制器方法上使用 `@JsonView` 来定义一个视图：

```java
@RestController
public class MyController {
    
    @GetMapping("/items/public-view")
    @JsonView(Views.Public.class)
    public Item getPublicItem() {
        // return your item
    }

    @GetMapping("/items/internal-view")
    @JsonView(Views.Internal.class)
    public Item getInternalItem() {
        // return your item
    }
}
```

这些方法将返回的 `Item` 对象序列化为 JSON，同时考虑到 `@JsonView` 定义的视图。

## 注意事项

- 使用 `@JsonView` 能够使你的 JSON 输出更加灵活，但请确保在复杂的序列化逻辑中不要过度使用它，以避免代码的可读性和可维护性降低。
- 在设计 API 时，始终要关注安全性。不要在公共视图中暴露敏感数据。