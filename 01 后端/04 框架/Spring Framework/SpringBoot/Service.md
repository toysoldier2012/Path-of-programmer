# @Page

在 Spring Data 中，`Page` 是一个主要的接口，用于封装分页相关的信息以及查询的结果。它是一种将查询结果与分页信息（如页码、页面大小、总记录数等）组合在一起的方式，使你能够轻松地在应用程序中实现分页功能。

### 主要方法

`Page` 接口提供了一些用于获取关于分页和查询结果的信息的方法，包括：

- `getContent()`: 获取当前页面的数据列表。
- `getTotalPages()`: 获取总的页面数。
- `getTotalElements()`: 获取总的元素数量（所有页面中的元素总数）。
- `getNumber()`: 获取当前页面的页码（通常基于0，意味着第一页的页码是0）。
- `getSize()`: 获取页面的大小（即每页的条目数）。
- `getSort()`: 获取用于查询的排序参数。

### 使用示例

在使用 Spring Data JPA 的情况下，通常会使用 `Page` 接口与 `PagingAndSortingRepository` 或 `JpaSpecificationExecutor` 结合使用来实现分页查询。

**示例 1：Repository**

```java
public interface OwnerRepository extends JpaRepository<Owner, Long> {
    Page<Owner> findAll(Pageable pageable);
}
```

**示例 2：Service**

在 Service 层，你可以调用定义的 `findAll` 方法，并传入一个 `Pageable` 对象（通常使用 `PageRequest.of(page, size)` 来创建）来执行分页查询。

```java
@Service
public class OwnerService {
    
    @Autowired
    private OwnerRepository ownerRepository;

    public Page<Owner> findOwners(int page, int size) {
        return ownerRepository.findAll(PageRequest.of(page, size));
    }
}
```

**示例 3：Controller**

在 Controller 层，你可以从 `Page` 对象获取信息并返回给客户端。

```java
@RestController
@RequestMapping("/owners")
public class OwnerController {

    @Autowired
    private OwnerService ownerService;

    @GetMapping
    public Page<Owner> getOwners(
            @RequestParam(name = "page", defaultValue = "0") int page,
            @RequestParam(name = "size", defaultValue = "10") int size) {
        return ownerService.findOwners(page, size);
    }
}
```

在这个示例中，`@RequestParam` 用于从请求参数中提取 `page` 和 `size` 的值，并提供默认值（当请求中没有提供这些参数时使用）。`Page` 对象既包含查询结果的列表（通过 `getContent()` 获取），也包含分页信息（如总页数和当前页数）。

这样，客户端就可以在获取数据的同时获得分页信息，并据此进行进一步的操作，比如实现分页导航功能。