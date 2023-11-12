
### 18. Which method of `Stream` can be used to **check whether a certain predicate matches at least one element in the stream**?

_Write the name of the **most efficient** method to do so_

### 19. 
What is the name of the method in the `java.lang.String` class that will test if the strings below **are empty or have only whitespace characters**?

```java
String str1 = "";               // yes
String str1 = "     ";          // yes
String str1 = "Hello world.";   // no
```

The expected method must be one that has existed since **Java version 11**.

### 20. Type the name of a class belonging to the package java. Lang which allows to concatenate efficiently strings of characters.

### 21. Which class can be used to store **thread-specific values**?

_Write only the name of the class_

### 22. 
```java
public class A {

    private A() {}

    private static class AHolder {
        private static final A INSTANCE = new A();
    }

    public static A getInstance() {
        return AHolder.INSTANCE; 
    }
}
```

What is the name of the design pattern used in this piece of code?

_Answer with 1 word only._

### 23. 
What method in `java.lang.String` would you use to split the string below into an array or collection of strings based on new lines?

```java
String str = "This is a string\nThis is the next line.\nHello world.";
```
