#junite 

`assertEquals`

``` java
assertEquals(expected, actual);
assertNotEquals();

assertNull();
assertNotNull();

assertSame();
assertNotSame();

assertTrue();
assertFalse();

assertArrayEquals();
assertIterableEquals();
assertLinesMatch();

assertThrows();
assertDoesNotThrow();

assertTimeoutPreemptively();
```

`assertEquals` 方法可以接受任何类型的对象作为参数。它使用 `Object.equals()` 方法来比较两个对象是否相等。如果要比较的两个对象不是同一类型的，则必须确保它们都实现了 `equals()` 方法，以便进行比较。

```java
@BeforeAll, @AfterAll
@BeforeEach, @AfterEach
@Test

@DisplayName, 
@DisplayNameGeneration(DisplayNameGenerator.Simple.class)
//Standard, Simple, ReplaceUnderscores, IndicativeSentences

@TestMethodOrder(MethodOrderer.MethodName.class)
//DisplayName, Methodname, Random, OrderAnnotation
@Order
```