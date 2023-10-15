#dto

**DTO**, 或 **Data Transfer Object**, 是一种设计模式的实现，用于减少多次网络或磁盘 I/O 操作的数量，通过一次传输获取或发送多个数据项，而不是一次一个。在对象-关系映射（ORM）和 API 开发中，DTO 通常用作一个数据容器，用于减少对外部系统、子系统或客户端的网络调用的数量，特别是在网络条件不理想的情况下。

### 主要特点：

- **数据封装**：DTO 封装了要传输的数据，通常只包含数据属性和其访问方法（getters 和 setters）。
    
- **不包含业务逻辑**：通常 DTO 只是一个“笨”对象，即它不包含任何业务逻辑，只用于数据传输。
    
- **可序列化**：DTO 对象通常需要可序列化，因为它们需要通过网络传输。
    
- **用于数据交换**：DTOs 通常用于不同系统或系统的不同层之间的数据交换。
    

### 为什么使用 DTO？

1. **降低网络负载**：通过将多个数据项组合到一个对象中，以减少网络传输的次数和负载。
    
2. **安全**：使用 DTO 可以控制客户端访问的数据，您可以选择暴露或隐藏数据模型中的特定部分。
    
3. **解耦**：DTO 可以与内部数据模型分开，允许模型自由变化，而不影响外部客户端的代码。
    

### DTO 示例（Java）

```java
public class UserDTO implements Serializable {

    private String username;
    private String email;
    // more fields...

    // Getters and Setters...
}
```
### DTO 在 Spring Boot REST API 中的使用：

你可能有一个实体类：

```java
@Entity
public class User {
    private Long id;
    private String username;
    private String password;
    private String email;
    // Getters and Setters...
}
```

但你可能不希望将所有字段（如密码）发送给客户端。这时候 DTO 可以派上用场：

```java
public class UserDTO {
    private String username;
    private String email;
    // Getters and Setters...
}
```

然后，在 API 调用中使用如 `ModelMapper` 的库或手动转换方法来转换 `User` 实体到 `UserDTO`。

### 总结：

- **DTO** 用于数据传输，尤其是在网络传输或跨系统交互的情况下。
    
- 它是一个数据容器，不包含业务逻辑，可确保数据的安全性和网络效率。
    
- 在多层架构中，DTO 可以作为各层之间的数据传输媒介，保持各层的解耦。

### Spring MVC 中使用 DTO

另一种常见的方法是使用 DTO。你可以为 `Pet` 创建一个 DTO 类，该类包含你想要在响应中返回的字段，然后在控制器中将你的实体映射到这个 DTO。

```java
public class PetDTO {
    private String name;
    private String type;
    private OwnerSimpleDTO owner;

    // getters and setters
}

public class OwnerSimpleDTO {
    private Long id;
    private String name;

    // getters and setters
}

@RestController
@RequestMapping("/pets")
public class PetController {
    //...

    @GetMapping
    public ResponseEntity<List<PetDTO>> getAllPets() {
        List<Pet> pets = petService.getAllPets();
        List<PetDTO> petDTOs = pets.stream()
                                   .map(pet -> modelMapper.map(pet, PetDTO.class)) 
                                   .collect(Collectors.toList());
        return new ResponseEntity<>(petDTOs, HttpStatus.OK);
    }
}
```

在这个示例中，我们使用了[ModelMapper](http://modelmapper.org/)来简化实体到DTO的映射过程。你也可以选择其他映射框架，或者手动进行映射。