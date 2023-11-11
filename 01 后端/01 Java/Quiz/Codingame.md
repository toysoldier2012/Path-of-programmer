
### 1 . Which options contain a **valid** Java 12+ switch expression?

_Multiple answers expected._

- 
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
    
- 
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
    
- 
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
    
- 
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
    
- 
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

### 2. Assuming you are working with Java 11+, select the **best** method to remove leading and trailing whitespace.

Example:

```java
String str = "    Hello world.    ";
```

- `str.trim()`
- `str.strip()`
- `str.removeTrailingWhitespace()`
- `str.trimWhitespace()`
- `str.stripLeading().stripTrailing()`

### 3. Consider the code below:

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

- 10
- Indeterminate value
- 0

### 4. Consider the code below:

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

- Shallow copy
- Deep copy

### 5. What will happen if a **synchronized method** is called by two threads on different object instances simultaneously?

- **Only one thread** **at a time** will access the method
- **Both threads** may access the method at the same time
- **Neither thread** will access the method and an exception will be thrown

### 6. In Java 11+, which API is the **best** one to make HTTP calls?

_Select the best answer._

- Classes in `java.net.http.*` such as `HttpClient`
- `java.net.HttpURLConnection`
- Third party APIs such as Apache HttpClient

### 7. Which **annotation** can be used to ensure that an interface is functional?

- @Functional
- @lambda
- @FunctionalInterface
- @abstract

### 8. What is the result of `2 >> 1` ?

- 0
- 1
- 2
- 3
- 4

### 9. In a base 2 system (binary), what is the value of `0001 & 0001` ?

- `0010`
- `0000`
- `0001`

### 10. The garbage collector ensures that there is enough memory to run a Java program.

- True
- False

### 11. Among these two solutions, which one do you prefer?  
  
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

- Solution #1
- Solution #2

### 12. Select the correct way of defining a **lambda function** in Java?

- 
```java
    ExampleInterface test = () -> 9;
    ```
    
- 
```java
    ExampleInterface test = () => 9;
    ```
    
- 
```java
    ExampleInterface test = () #> 9;
    ```
    
- 
```java
    ExampleInterface test = () >> 9;
    ```

### 13. 
```java
int i1 = 5;
int i2 = 2;
int i3 = i1 / i2;
```

What is the value of `i3`?

- 3
- 2.5
- 2
- NaN

### 14. You are implementing a library. Among these options, which one do you select to manage an unexpected behavior?

- `throw new UnexpectedBehaviorException()`
- `System.exit(-1)`
- `System.err.println("Error: unexpected behavior")`
- `return false`

### 15. Which method is called when a thread is executed?

- do
- run
- exec
- execute
- Play

### 16. Privates attributes are visible from subclasses. 

- True
- False

### 17. In Java 8, interfaces can contain concrete methods.

- True
- False

# Text

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

# Code

### 24. 
You don’t remember where you saved the file `universe-formula`. The only thing you remember about this file is you put it somewhere in a sub-folder of `/tmp/documents`.  
  
Implement the method `String locateUniverseFormula()` to locate `universe-formula` and then return **the absolute path of the file** (from the file system root).

- `/tmp/documents` can contain nested sub-folders and `universe-formula` can belong to any one of them.
- If `universe-formula` cannot be found, then your program should return `null`.

Example :  
`locateUniverseFormula()` returns `/tmp/documents/a/b/c/universe-formula` if `universe-formula` is found inside the folder `/tmp/documents/a/b/c`.

### 25. 
We consider the sequence of numbers where a number is followed by **the same number plus the sum of its digits**.

For example `34` is followed by `41` (as 41 = 34 + (3 + 4)). `41` is itself followed by `46` (46 = 41 + (4 + 1)).

Two sequences which start from different numbers may **join at a given point**, for example, the sequence starting from `471` and the sequence starting from `480` share the number `519` (**the join point**) in their sequence. After the join point, the sequences are equal.

![](https://static.codingame.com/work/servlet/fileservlet?id=29075214099447)

_An example of two sequences joining at 519._ 

Implement the method `int computeJoinPoint(int s1, int s2)` which takes the starting points of two sequences and then returns the join point of these sequences.

Constraints:

- The given sequences always join
- 0 < `s1, s2` < 20000000
- 0 < join point < 20000000

### 26. 
The goal of this exercise is **to find the endpoint node** of a simple network.

In this simple network, each node is linked to at most one outgoing node in a **one way** **forward** direction.

![](https://static.codingame.com/work/servlet/fileservlet?id=27057673253517)

_A simple network example_

Implement method `findNetworkEndpoint(startNodeId, fromIds, toIds)` which should return the last node id of the network found when starting from the node with id `startNodeId` and following the links of the network.

In the above example, the endpoint node when starting from node #2 (or any other node) is node #5.

`fromIds` and `toIds` are two arrays of the same length which describe the one-way links of the network (`fromIds[i]` is linked to `toIds[i]`). In the example above, `fromIds` is:

```cross
[1, 7, 3, 4, 2, 6, 9]
```

and `toIds` is:

```cross
[3, 3, 4, 6, 6, 9, 5]
```

**In case you run into a loop** when traversing the network, the method should return the id of the last node traversed **before** closing the loop.

Constraints:

- 0 < number of links < 10000
- A node cannot be directly linked to itself

### 27 . 
Write a program which returns the current state of a tennis game.

_// REMINDER OF THE TENNIS RULES //_

A tennis game is played as follows:

- First score  = 15 points
- Second score = 30 points
- Third score = 40 points

After a player reaches 40 points, he or she can:

- Enter a **DEUCE** state if both players have scored the same number of times
- Enter an **ADVANTAGE** state if both players scored at least three times AND the player scored one time more than his or her opponent
- **WIN** the game if he or she has scored at least four times AND two times more than the other player

![](https://static.codingame.com/work/servlet/fileservlet?id=37457292922763)

Implement the method `computeGameState(nameP1, nameP2, wins)` which returns the current state of a game.

**Parameters:**

- `nameP1`, the name of the first player as a string
- `nameP2`, the name of the second player as a string
- `wins`, an array of strings listing the name of each ball's winner

**Expected Result:**

The current state of the game as a string:

- `P1 0 - P2 0` (with players' names in the same order as given in parameters)
- `P1 15 - P2 30`
- `15a` (in case of a 15-15 draw)
- `30a` (in case of a 30-30 draw)
- `P2 WINS`
- `DEUCE`
- `P1 ADVANTAGE`
- ...

**EXAMPLE:**

**Parameters**

Bob

Anna

Bob, Anna, Bob

**Result**

Bob 30 - Anna 15

### 28 .
### Objective

Your avatar is in a strange world with two inter-dimensional, bidirectional portals. Write a program that returns the coordinates of your avatar given a series of moves and the location of the portals.

![](https://static.codingame.com/work/servlet/fileservlet?id=38287530564005)

### How it works

- The map is represented by a grid of `width` squares wide and `height` squares high.
- The top left square is located at `(0, 0)` where the first integer represents the column and the second the row.
- The initial positions of your avatar and the two portals are given by arrays of two integers `position`, `portalA`, and `portalB`.
- `moves`, is a string composed of the characters `U` (top), `D` (down), `R` (right), `L` (left).

If your avatar walks from a given square to a square with a portal, he teleports to the associated portal (and stays on that target square until he makes another move). If a movement would make your avatar move past the end of the map, he does not move nor teleport.

### Implementation

Implement the method `computeFinalPosition(width, height, position, portalA, portalB, moves)` which:

- takes as inputs the integers `width`, `height`, the integer arrays `position`, `portalA`, `portalB`, and the string `moves` with :
    - 0 < `width` < 20
    - 0 < `height` < 20
    - 0 <= number of characters in `moves` <= 255
- and returns the final position of your avatar as an array of two integers.

### Example

![](https://static.codingame.com/work/servlet/fileservlet?id=39297999963943)

### 29.
Implement the method `encode(plainText)` which returns an encoded message.

It receives a `plainText` string parameter, for example `aaaabcccaaa`.

You must encode it by counting each consecutive sequence of a letter. e.g. in `aaaabcccaaa`, there are:

- 4 times the letter `a`
- then 1 `b`
- then 3 `c`
- then 3 `a`

Therefore you must return the string `4a1b3c3a`.

Constraints :

- `plainText` is made of lowercase letters: **a**-**z**
- `plainText` is never `null` and has a maximum length of 15000 characters

**EXAMPLES:**

**PlainText**

aabaa

**EncodedText**

2a1b2a

**PlainText**

aaaabcccaaa

**EncodedText**

4a1b3c3a

### 30.

In this exercise we will calculate an approximation of π (Pi).

The technique is as follows: 

Take a random point P at coordinate (x, y) such that `0 ≤ x ≤ 1` and `0 ≤ y ≤ 1`. If `x² + y² ≤ 1`, then the point is inside the quarter disk of radius `1`, otherwise the point is outside.

 

![](https://static.codingame.com/work/servlet/fileservlet?id=1306271420)

Fig 1. An example using 33 random points.

We know that the probability that the point is inside the quarter disk is equal to `π/4`.

Write the method `double approx(double[][] pts)` who will use the points `pts` to return an approximation of the number π.

**Input:**

- Each item in `pts` is a point.
- A point is represented by an array containing exactly two numbers, respectively, `x` and `y` such that `0 ≤ x ≤ 1` and `0 ≤ y ≤ 1`.
- `pts` is never null and always contains at least one item.

### 31.

The `reshape(n, str)` method should return the string `str` without spaces and layed out in lines of at most `n` characters.  
  
Examples:

|**Call**|**Returned String**|
|---|---|
|reshape(3, "abc de fghij")|abc<br>def<br>ghi<br>j|
|reshape(2, "1 23 456")|12<br>34<br>56|
  
**Write the body of the `reshape(n, str)` method.**

**Note:** Do not add a trailing `\n` character.

### 32
In order to detect errors on identification numbers, a check digit is often added at the end of that number.

Implement the method `computeCheckDigit(identificationNumber)` that takes a number (as a string) and returns the check digit, using the following algorithm:

- Sum the digits in the even-numbered positions (positions 0, 2, 4, etc.).
- Multiply the result by three.
- Add the digits in the odd-numbered positions to the result (positions 1, 3, 5, etc.).
- Take the last digit of the result.
- If it's not 0, subtract this digit from 10. Otherwise, keep it as 0.
- Return the result

_(Assuming that the first digit on the left has the position 0)_

  
**Example:**

Given the identification number `39847` :

- Sum the digits in the even-numbered positions: `3 + 8 + 7 = 18`
- Multiplied by three: `18 x 3 = 54`
- Add the digits in the odd-numbered positions: `54 + (9 + 4) = 67`
- Last digit: `7`
- Subtract 7 from 10: `10 - 7 = 3`

The expected result is `3` for `39847`.

**Constraints:**

The length of `identificationNumber` can vary from 1 to 12 characters.

### 33
### Objective

Javanais, also known as "_Langue de feu_" (fire language), is a slang coding process that was used in the late 19th century by some criminals to encrypt their conversations. Write a program that returns the Javanais translation of a sentence.

### How it works

- Before each of the following vowel (a, e, i, o, u), insert the parasitic syllable "av" ;
- Unless the vowel is preceded by another vowel.

### Implementation

Implement the method `translate(text)` which:

- takes as input `text`, a string of fewer than 255 characters ;
- returns the Javanais translation as a string.

For simplicity, the inputs contain only lowercase letters.

### Example

![](https://static.codingame.com/work/servlet/fileservlet?id=39072371100548)

### 34
`AsciiArt.printChar` displays exactly one ASCII character from A to Z (inclusive) on multiple rows and columns.

Now, we want to do the reverse operation: to get a character from its graphic representation.

Implement the method `scanChar(String s)` so that it returns the character associated with the graphical representation provided by `AsciiArt.printChar(char c)`. If `s` does not match a character from A to Z (inclusive), then `scanChar` must return the character `?`.

### 35
`StreamPrinter.print(Reader reader)` is not robust.  
  
Improve `StreamPrinter.print(Reader reader)`.

### 36
Today, stores are increasingly equipped with automated checkout machines. Most of these machines accept payment only by credit card, despite the fact that a significant portion of consumers continue to pay for goods with cash.  
  
One of the problems presented by cash transactions is how to return change: what is the optimal way to give back a certain amount, with the minimum number of coins and bills? It’s an issue that each of us encounters on a daily basis and the problem is the same for automated checkout machines.  
  
In this exercise, you are asked to try and find an optimal solution for returning change in a very specific case: when the machine contains only **€****2** coins, **€****5** bills and **€****10** bills.  
  
To simplify the problem, we imagine that all of these coins and bills are available in **unlimited quantities**.  
  
Here are some examples of how change may be returned:

|**Change for**|**Possible Solutions**|**Optimal Solution**|
|---|---|---|
|€1|Impossible|Impossible|
|€6|€2 + €2 + €2|€2 + €2 + €2|
|€10|€2 + €2 + €2 +€2 + €2<br><br>€5 + €5<br><br>€10|€10|
|€9223372036854775807|...|(€10 * 922337203685477580) + €5 + €2|

  
Change is represented as a `Change` object. This object has three properties: `coin2`, `bill5` and `bill10` which represents the numbers of €2 coins, €5 bills and €10 bills.  
  
For instance, when applied to example #2 of the table above (€6), we should get a `Change` object with the following values:

- `coin2` value is 3 (3 €2 coins)
- `bill5` value is 0 (no €5 bill)
- `bill10` value is 0 (no €10 bill)

Implement the `optimalChange(long s)` method which returns a `Change` object. The sum of coins and bills indicated in the `Change` object must be `s`. If it is not possible to give back change – as in example #1 –, the method must return `null`.  
  
To get a maximum number of points, your solution should always provide a result – when possible – having the minimal number of bills and coins.  
  
Constraints:  
`s` is a `long`.
0 < `s` <= 9223372036854775807

### 37
![[Pasted image 20231111215659.png]]
![[Pasted image 20231111215710.png]]
### 38
![[Pasted image 20231111215617.png]]

### 39
![[Pasted image 20231111215748.png]]
### 40
![[Pasted image 20231111215818.png]]
### 41
![[Pasted image 20231111215838.png]]