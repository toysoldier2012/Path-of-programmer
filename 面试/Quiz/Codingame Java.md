
# QCM

### Which **annotation** can be used to ensure that an interface is functional?

- [ ] @Functional
- [ ] @lambda
- [ ] @FunctionalInterface
- [ ] @abstract

### What will happen if a **synchronized method** is called by two threads on different object instances simultaneously?

- [ ] **Only one thread** **at a time** will access the method
- [ ] **Both threads** may access the method at the same time
- [ ] **Neither thread** will access the method and an exception will be thrown

### Anticipating the result of a code

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

### In Java 11+, which API is the **best** one to make HTTP calls?

_Select the best answer._

- [ ] Classes in `java.net.http.*` such as `HttpClient`
- [ ] `java.net.HttpURLConnection`
- [ ] Third party APIs such as Apache HttpClient

### Among these two solutions, which one do you prefer?  
  
Solution #1 :

```java
interface FlyAble {
    void fly();
}
abstract class AirPlane implements FlyAble {}
abstract class Bird implements FlyAble {}​
```
  
Solution #2 :  

```java
abstract class AirPlane {
    abstract void fly();
}
abstract class Bird extends AirPlane {}​
```

- [ ] Solution #1
- [ ] Solution #2

### In Java 8, interfaces can contain concrete methods.

- [ ] True
- [ ] False

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
### Operation on integers
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

### Which method is called when a thread is executed?

- [ ] do
- [ ] run
- [ ] exec
- [ ] execute
- [ ] Play

### Shallow vs Deep copy

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

### Which options contain a **valid** Java 12+ switch expression?

*Multiple answers expected.*

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

### You are implementing a library. Among these options, which one do you select to manage an unexpected behavior?

- [ ] `throw new UnexpectedBehaviorException()`
- [ ] `System.exit(-1)`
- [ ] `System.err.println("Error: unexpected behavior")`
- [ ] `return false`

### Privates attributes are visible from subclasses. 

- [ ] True
- [ ] False

### Parmi les expressions Lambda suivantes, quelle est celle qui évaluera correctement une instance de `Supplier<String>` ? 

- [ ] (s) -> s s.substring(1) 
- [ ] ()->" john " 
- [ ] 0 \to {return "Helen"; } 

### Parmi ces deux procedures de développement, laquelle préconisez-vous ?
Procedure #1 :
1. Ecrire des tests pour la nouvelle fonctionnalité "F"
2. Tester que "F" ne fonctionne pas
3. Implémenter "F"
4. Tester que "F" fonctionne correctement
Procedure #2 :
1. Implementer la nouvelle fonctionnalité "F"
2. Ecrire des tests pour "F"
3. Tester que "" fonctionne correctement

### En Java 9+, quelle annotation et metadata permet de signaler aux utilisateurs d'une APl publique que vous maintenez qu'une fonctionnalité sera supprimée dans le futur ?

`@Deprecated` `forRemoval` et `since`

### Quelles sont les propositions justes? 

Plusieurs réponses acceptées. 

- [ ] Une Map associe des valeurs de n'importe quel type à des clefs sous forme de String
- [ ] Une HashMap utilise equals() et hashcode() des clés pour retrouver une valeur
- [ ] Les valeurs d'une HashMap sont rangées dans l'ordre chronologique de leurs insertions
- [ ] Une HashMap peut contenir une et une seule clef 'null'
- [ ] Une HashMap peut contenir une et une seule valeur 'null'
- [ ] Une Map peut contenir plusieurs fois la même valeur
- [ ] Une Map peut contenir plusieurs fois la même clef
- [ ] Les valeurs d'une TreeMap sont triées suivant l'ordre ascendant de leurs clefs ou d'un comparateur sur ces dernières.

### Quelles sont les propositions justes? 

Plusieurs réponses acceptées. 

- [ ] un thread possède son propre espace mémoire
- [ ] le 'main' est exécuté dans un thread
- [ ] un thread peut continuer de s'exécuter une fois la jvm arrété
- [ ] un thread peut bloquer l'arrêt de la jvm
- [ ] à l'exécution, il est possible de savoir quel est le thread courant
- [ ] sur une machine multi-coeurs, tous les threads s'executent dans un seul processus et donc dans un seul coeur
- [ ] pour faire des traitements asynchrones il est nécessaire d'utiliser directement ou indi- rectement des threads.

# Text

### Design pattern 01

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

### Design pattern

You are writing an application aiming at making cocktails. A cocktail contains several ingredients (according to the customer's order) and it can quickly become complex to prepare. However, the different steps in the preparation process remain the same: adding an alcohol, adding a syrup, etc. If you know a design pattern that would be appropriate to prepare these cocktails, type its name in the text field (1 word only).

### java. lang. String. lines ()

What method in `java.lang.String` would you use to split the string below into an array or collection of strings based on new lines?

```java
String str = "This is a string\nThis is the next line.\nHello world.";
```

### Stream anyMatch () method

Which method of `Stream` can be used to **check whether a certain predicate matches at least one element in the stream**?

_Write the name of the **most efficient** method to do so_

### String buffers

Type the name of a class belonging to the package java. Lang which allows to concatenate efficiently strings of characters.

### String.isBlank ()

What is the name of the method in the `java.lang.String` class that will test if the strings below **are empty or have only whitespace characters**?

```java
String str1 = "";               // yes
String str1 = "     ";          // yes
String str1 = "Hello world.";   // no
```

The expected method must be one that has existed since **Java version 11**.

### ThreadLocal use

Which class can be used to store **thread-specific values**?

_Write only the name of the class_

