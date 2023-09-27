#junite 

`assertEquals`

``` java
assertEquals(expected, actual);
```

`assertEquals` 方法可以接受任何类型的对象作为参数。它使用 `Object.equals()` 方法来比较两个对象是否相等。如果要比较的两个对象不是同一类型的，则必须确保它们都实现了 `equals()` 方法，以便进行比较。

@BeforeTest, @AfterTest, @Test