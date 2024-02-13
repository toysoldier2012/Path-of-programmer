#lombok

# @Data

在 Java 开发中，`@Data` 是 Lombok 库提供的一个注解，用于简化数据类的代码量。当你在一个类上使用 `@Data` 注解时，Lombok 会在编译时自动为这个类生成各种常用的代码，包括：

1. **@Getters**: 为所有字段生成 getter 方法。
2. **@Setters**: 为所有非 final 字段生成 setter 方法。
3. **@EqualsAndHashCode**: 生成一个用于比较对象相等性的 `equals` 方法，该方法会考虑类中的所有非静态字段。
4. **@ToString**: 生成一个 `toString` 方法，该方法会打印对象的字符串表示形式，包括类名和所有字段的名字及其值。
5. **@RequiredArgsConstructor**: 生成一个构造方法，该方法会接受所有非初始化和非 `null` 的 final 字段作为参数。

### 注意：

- **不要滥用**: `@Data` 是一个功能强大但较重的注解，它生成很多方法，有时候我们可能并不需要这些全部功能。Lombok 提供了其他的注解如 `@Getter`、`@Setter`、`@ToString` 等，可以让我们更精确地控制要生成的代码。
    
- **equals 和 hashCode 的使用**：在实体类（尤其是 JPA 实体）上谨慎使用 Lombok 的 `@Data` 或 `@EqualsAndHashCode`，因为它们生成的 `equals` 和 `hashCode` 方法可能会考虑实体的所有字段，这在某些情况下可能不是你想要的（例如，懒加载的字段）。在这些情况下，最好自定义 `equals` 和 `hashCode` 的实现。
    

使用 Lombok 能够显著简化你的模型类的代码，让你的代码更加清晰和简洁，但也要留意上述的一些细节和潜在问题。