#mockito



```java
when().thenReturn();
when().thenThrow();
when().thenThrow().thenReturn();
```


# doAweser

`doAnswer`是Mockito框架中的一个方法，用于为模拟对象的方法调用提供自定义的响应。当你想要在模拟对象的方法被调用时执行一些自定义逻辑，而不仅仅是返回一个简单的值时，`doAnswer`特别有用。这使得你能够检查方法调用的参数，或者基于这些参数改变模拟对象的行为。

在提供的例子中，`doAnswer`用于捕获对`setEntity`方法的调用，并允许我们访问传递给该方法的参数。通过这种方式，我们可以检查设置到`HttpPost`对象的`HttpEntity`是否包含了正确的JSON字符串。

### 解析示例中的doAnswer部分

```java
doAnswer(invocation -> {
    HttpEntity actualEntity = invocation.getArgument(0);
    // 验证实体内容
    String content = EntityUtils.toString(actualEntity, StandardCharsets.UTF_8);
    assert content.equals(json) : "The JSON entity does not match the expected content.";
    return null;
}).when(mockPost).setEntity(any(HttpEntity.class));
```

这段代码的工作流程如下：

1. **模拟行为设置**：`doAnswer`接受一个`Answer`对象作为参数，这里通过Lambda表达式提供了`Answer`的实现。`Answer`接口定义了一个`answer`方法，该方法在模拟对象的相应方法被调用时执行。
    
2. **捕获方法调用**：当`mockPost.setEntity(any(HttpEntity.class))`被调用时，提供给`doAnswer`的Lambda表达式将被执行。这里`any(HttpEntity.class)`是参数匹配器，表示我们不关心具体传递什么参数，任何`HttpEntity`对象都匹配。
    
3. **访问调用参数**：`invocation.getArgument(0)`用于获取第一个参数（索引从0开始），在这个例子中，它是传递给`setEntity`方法的`HttpEntity`对象。
    
4. **自定义逻辑**：接着，我们将`HttpEntity`转换成字符串，并与预期的JSON字符串进行比较。如果不匹配，将抛出一个断言错误。
    
5. **返回值**：`Answer`的`answer`方法需要返回一个对象，这个对象会被视为模拟方法的返回值。在这个例子中，由于`setEntity`方法的返回类型是`void`，我们返回`null`。