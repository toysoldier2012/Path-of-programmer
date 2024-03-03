
# Jackson

```java 
// 使用Jackson序列化对象 
ObjectMapper mapper = new ObjectMapper(); 
String jsonString = mapper.writeValueAsString(user);
```

在model层中使用`@JsonProperty`注解，来指定JSON属性的名称

```java
import com.fasterxml.jackson.annotation.JsonProperty;

public class User {
    @JsonProperty("user_name")
    private String username;
    private String password;

    // 构造函数、getters和setters
}
```

# Gson

```java
// 使用Gson序列化对象 
Gson gson = new Gson(); 
String jsonString = gson.toJson(user);
```

在model层中使用`@SerializedName`注解，来指定JSON属性的名称

```java
import com.google.gson.annotations.SerializedName;

public class User {
    @SerializedName("user_name")
    private String username;
    private String password;

    // 构造函数、getters和setters
}
```