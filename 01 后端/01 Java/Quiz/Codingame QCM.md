




### Which **annotation** can be used to ensure that an interface is functional?

- [ ] @Functional
- [ ] @lambda
- [ ] @FunctionalInterface
- [ ] @abstract

### Which options contain a **valid** Java 12+ switch expression?

_Multiple answers expected._

- [ ]  
```java
    int state = switch (month) {
        case JANUARY  -> 0;
        case FEBRUARY -> 1;
        case MARCH    -> 2;
        default       -> {
            int l = logic(month);
            l *= 9;
            yield l;
        }
    };
    ```
    
- [ ] 
```java
    int number = switch (state) {
        case "UP": 
            yield 5;
        case "DOWN":
            yield 7;
        default:
            System.out.println("Illegal state");
            yield -1;
    };
    ```
    
- [ ] 
```java
    int number = switch (state) {
        case "UP": 
            break 5;
        case "DOWN":
            break 7;
        default:
            System.out.println("Illegal state");
            break -1;
    };
    ```
    
- [ ] 
```java
    int state = switch (month) {
        case JANUARY  -> 0;
        case FEBRUARY -> 1;
        case MARCH    -> 2;
        default       -> {
            int l = logic(month);
            l *= 9;
            return l;
        }
    };
    ```
    
- [ ] 
```java
    int number = switch (state) {
        case "UP": 
            return 5;
        case "DOWN":
            return 7;
        default:
            System.out.println("Illegal state");
            return -1;
    };
    ```

### Assuming you are working with Java 11+, select the **best** method to remove leading and trailing whitespace.

Example:

```java
String str = "    Hello world.    ";
```

- [ ] `str.trim()`
- [ ] `str.strip()`
- [ ] `str.removeTrailingWhitespace()`
- [ ] `str.trimWhitespace()`
- [ ] `str.stripLeading().stripTrailing()`

### Consider the code below:

```java
public abstract class Shape {

    private int surface;

    public Shape() {
        this.surface = computeSurface();
    }

    protected abstract int computeSurface();

    public int getSurface() {
        return surface;
    }
}

public class SquareShape extends Shape {
    private final int size;

    public SquareShape(int size) {
        this.size = size;
    }

    @Override
    protected int computeSurface() {
        return size * size;
    }
}
```

Then, the following code is executed, which uses the classes defined above:

```java
SquareShape squareShape = new SquareShape(10);
int mySurface = squareShape.getSurface();
```

What will be the value of the variable `mySurface`?

- [ ] 10
- [ ] Indeterminate value
- [ ] 0

### Consider the code below:

```java
public static void main(String[] args) throws CloneNotSupportedException {

        LinkedList<Player> players1 = new LinkedList<>();
        Player p1 = new Player();
        p1.setBattingAverage(46.7 f);
        p1.setWorldRank(4);

        Player p2 = new Player();
        p2.setBattingAverage(56.9 f);
        p2.setWorldRank(1);

        players1.add(p1);
        players1.add(p2);

        LinkedList<Player> players2 = new LinkedList<>();
        for (Player p : players1) {
            players2.add(p);
        }
        
        players2.get(0).setWorldRank(5);

    }
```

A list of players has been created, together with a copy of that list. What type of **copying method** has been implemented? 

- [ ] Shallow copy
- [ ] Deep copy

### What will happen if a **synchronized method** is called by two threads on different object instances simultaneously?

- [ ] **Only one thread** **at a time** will access the method
- [ ] **Both threads** may access the method at the same time
- [ ] **Neither thread** will access the method and an exception will be thrown

### In Java 11+, which API is the **best** one to make HTTP calls?

_Select the best answer._

- [ ] Classes in `java.net.http.*` such as `HttpClient`
- [ ] `java.net.HttpURLConnection`
- [ ] Third party APIs such as Apache HttpClient



### What is the result of `2 >> 1` ?

- [ ] 0
- [ ] 1
- [ ] 2
- [ ] 3
- [ ] 4

### In a base 2 system (binary), what is the value of `0001 & 0001` ?

- [ ] `0010`
- [ ] `0000`
- [ ] `0001`

### The garbage collector ensures that there is enough memory to run a Java program.

- [ ] True
- [ ] False

### Among these two solutions, which one do you prefer?  
  
Solution #1:

```java
interface FlyAble {
    void fly();
}
abstract class AirPlane implements FlyAble {}
abstract class Bird implements FlyAble {}​
```
  
Solution #2:  

```java
abstract class AirPlane {
    abstract void fly();
}
abstract class Bird extends AirPlane {}​
```

- [ ] Solution #1
- [ ] Solution #2

### Select the correct way of defining a **lambda function** in Java?

- [ ] 
```java
    ExampleInterface test = () -> 9;
    ```
    
- [ ] 
```java
    ExampleInterface test = () => 9;
    ```
    
- [ ] 
```java
    ExampleInterface test = () #> 9;
    ```
    
- [ ] 
```java
    ExampleInterface test = () >> 9;
    ```

###  
```java
int i1 = 5;
int i2 = 2;
int i3 = i1 / i2;
```

What is the value of `i3`?

- [ ] 3
- [ ] 2.5
- [ ] 2
- [ ] NaN

### You are implementing a library. Among these options, which one do you select to manage an unexpected behavior?

- [ ] `throw new UnexpectedBehaviorException()`
- [ ] `System.exit(-1)`
- [ ] `System.err.println("Error: unexpected behavior")`
- [ ] `return false`

### Which method is called when a thread is executed?

- [ ] do
- [ ] run
- [ ] exec
- [ ] execute
- [ ] Play

### Privates attributes are visible from subclasses. 

- [ ] True
- [ ] False

### In Java 8, interfaces can contain concrete methods.

- [ ] True
- [ ] False

Parmi les expressions Lambda suivantes, quelle est celle qui évaluera correctement une instance de `Supplier<String>` ? 
1. (s) -> s s.substring(1) 
2. ()->" john " 
3. 0 \to {return "Helen"; } 
Une seule réponse acceptée.