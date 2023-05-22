
https://github.com/Ebazhanov/linkedin-skill-assessments-quizzes/blob/main/java/java-quiz.md

#### Q1. Given the string "strawberries" saved in a variable called fruit, what would `fruit.substring(2, 5)` return? #string 

- [ ] rawb
- [x] raw
- [ ] awb
- [ ] traw


#### Q2. How can you achieve runtime polymorphism in Java? #polymorphism

- [ ] method overloading
- [ ] method overrunning
- [x] method overriding
- [ ] method calling


#### Q3. Given the following definitions, which of these expression will **NOT** evaluate to true? #operator 

`boolean b 1 = true, b 2 = false; int i 1 = 1, i 2 = 2;`
- [ ] `(i1 | i2) == 3`
- [x] `i2 && b1`
- [ ] `b1 || !b2`
- [ ] `(i1 ^ i2) < 4`


#### Q4. What is the output of this code? #array 

```java

1: class Main {

2:   public static void main (String[] args) {

3:     int array[] = {1, 2, 3, 4};

4:     for (int i = 0; i < array.size(); i++) {

5:        System.out.print(array[i]);

6:     }

7:   }

8: }

```

- [x] It will not compile because of line 4.
- [ ] It will not compile because of line 3.
- [ ] 123
- [ ] 1234

> [!note] 
> `array.length`
> `string.length()`
> `collection.size()`


#### Q5. Which of the following can replace the CODE SNIPPET to make the code below print "Hello World"? #interface

```java

interface Interface1 {

    static void print() {

        System.out.print("Hello");

    }

}

  

interface Interface2 {

    static void print() {

        System.out.print("World!");

    }

}

```

- [ ] `super1.print(); super2.print();`
- [ ] `this.print();`
- [ ] `super.print();`
- [x] `Interface1.print(); Interface2.print();`


#### Q6. What does the following code print? #string 

```java

String str = "abcde";

str.trim();

str.toUpperCase();

str.substring(3, 4);

System.out.println(str);

```

- [ ] CD
- [ ] CDE
- [ ] D
- [x] abcde


#### Q7. What is the result of this code? #exception 

```java
class Main {
    public static void main (String[] args){
        System.out.println(print(1));
    }
    static Exception print(int i){
        if (i>0) {
            return new Exception();
        } else {
            throw new RuntimeException();
        }
    }
}
```

- [ ] It will show a stack trace with a runtime exception.
- [x] "java.lang.Exception"
- [ ] It will run and throw an exception.
- [ ] It will not compile.


#### Q8. Which class can compile given these declarations? #interface 

```java
interface One {
    default void method() {
        System.out.println("One");
    }
}

interface Two {
    default void method () {
        System.out.println("One");
    }
}
```

- [ ] A

```java
class Three implements One, Two {
    public void method() {
        super.One.method();
    }
}
```

- [ ] B

```java
class Three implements One, Two {
    public void method() {
        One.method();
    }
}
```

- [ ] C

```java
class Three implements One, Two {
}
```

- [x] D

```java
class Three implements One, Two {
  public void method() {
    One.super.method();
  }
}
```

> [!note] 
>  interface.super.method()


#### Q9. What is the output of this code? #arraylist 

```java
class Main {
  public static void main (String[] args) {
	    List list = new ArrayList();
	    list.add("hello");
	    list.add(2);
		System.out.print(list.get(0) instanceof Object);
	    System.out.print(list.get(1) instanceof Integer);
    }
}
```

- [ ] The code does not compile.
- [ ] truefalse
- [x] truetrue
- [ ] falsetrue


#### Q10. Given the following two classes, what will be the output of the Main class #package 

```java

package mypackage;

public class Math {

    public static int abs(int num){

        return num < 0 ? -num : num;

    }

}

package mypackage.elementary;

public class Math {

    public static int abs (int num) {

        return -num;

    }

}

```

```java

import mypackage.Math;

import mypackage.elementary.*;

  

class Main {

    public static void main (String args[]){

        System.out.println(Math.abs(123));

    }

}

```

- [ ] Lines 1 and 2 generate compiler errors due to class name conflicts.
- [ ] "-123"
- [ ] It will throw an exception on line 5.
- [x] "123"

> [!note] 
> **Explanation:** The answer is "123". The `abs()` method evaluates to the one inside mypackage.Math class, because the import statements of the form: 


#### Q 11. What is the result of this code?

```java

1: class MainClass {
2:     final String message() {
3:         return "Hello!";
4:     }
5: }

6: class Main extends MainClass {
7:     public static void main(String[] args) {
8:         System.out.println(message());
9:     }

10:     String message() {
11:         return "World!";
12:     }
13: }
```

- [x] It will not compile because of line 10.
- [ ] "Hello!"
- [ ] It will not compile because of line 2.
- [ ] "World!"


#### Q 12. Given this code, which command will output "2"? #compiler 

```java

class Main {

    public static void main(String[] args) {

        System.out.println(args[2]);

    }

}

```

- [ ] `java Main 1 2 "3 4" 5`
- [x] `java Main 1 "2" "2" 5`
- [ ] `java Main.class 1 "2" 2 5`
- [ ] `java Main 1 "2" "3 4" 5`

> [!note] 
>  javac MyProgram.java
java MyProgram 1 "2" "2" 5


#### Q13. What is the output of this code? #primitivedatatype  

```java

class Main {

    public static void main(String[] args){

        int a = 123451234512345;

        System.out.println(a);

    }

}

```

- [ ] "123451234512345"
- [x] Nothing - this will not compile.
- [ ] a negative integer value
- [ ] "12345100000"

> [!note] 
> int 32 位，大概 10 位数


#### Q 14. What is the output of this code? #string 

```java

class Main {

    public static void main (String[] args) {

        String message = "Hello world!";

        String newMessage = message.substring(6, 12)

            + message.substring(12, 6);

        System.out.println(newMessage);

    }

}

```

- [ ] The code does not compile.
- [x] A runtime exception is thrown.
- [ ] "world!!world"
- [ ] "world!world!"


#### Q15. How do you write a foreach loop that will iterate over ArrayList\<Pencil\>pencilCase? #arraylist 

- [x] `for (Pencil pencil : pencilCase) {}`
- [ ] `for (pencilCase.next()) {}`
- [ ] `for (Pencil pencil : pencilCase.iterator()) {}`
- [ ] `for (pencil in pencilCase) {}`


#### Q 16. What does this code print? #comparable

```java

System.out.print("apple".compareTo("banana"));

```

- [ ] `0`
- [ ] positive number
- [x] negative number
- [ ] compilation error


#### Q 17. You have an ArrayList of names that you want to sort alphabetically. Which approach would **NOT** work? #list

- [ ] `names.sort(Comparator.comparing(String::toString))`
- [ ] `Collections.sort(names)`
- [x] `names.sort(List.DESCENDING)`
- [ ] `names.stream().sorted((s1, s2) -> s1.compareTo(s2)).collect(Collectors.toList())`

> [!note] 
>  详见 list 比较方式


#### Q 18. By implementing encapsulation, you cannot directly access the class's \_ properties unless you are writing code inside the class itself. #encapsulation

- [x] private
- [ ] protected
- [ ] no-modifier
- [ ] public


#### Q 19. Which is the most up-to-date way to instantiate the current date? #date

- [ ] `new SimpleDateFormat("yyyy-MM-dd").format(new Date())`
- [ ] `new Date(System.currentTimeMillis())`
- [x] `LocalDate.now()`
- [ ] `Calendar.getInstance().getTime()`


#### Q 20. Fill in the blank to create a piece of code that will tell whether `int 0` is divisible by `5`:

`boolean isDivisibleBy5 = _____`

- [ ] `int0 / 5 ? true: false`
- [x] `int0 % 5 == 0`
- [ ] `int0 % 5 != 5`
- [ ] `Math.isDivisible(int0, 5)`


#### Q 21. How many times will this code print "Hello World!"? #operator 

```java

class Main {

    public static void main(String[] args){

        for (int i=0; i<10; i=i++){

            i+=1;

            System.out.println("Hello World!");

        }

    }

}

```

- [x] 10 times
- [ ] 9 times
- [ ] 5 times
- [ ] infinite number of times


#### Q 22. The runtime system starts your program by calling which function first? #class  

- [ ] print
- [ ] iterative
- [ ] hello
- [x] main


#### Q 23. What code would you use in Constructor A to call Constructor B? #class

```java

public class Jedi {

  /* Constructor A */

  Jedi(String name, String species){}


  /* Constructor B */

  Jedi(String name, String species, boolean followsTheDarkSide){}

}

```

- [ ] Jedi(name, species, false)
- [ ] new Jedi(name, species, false)
- [x] this(name, species, false)
- [ ] super(name, species, false)


#### Q 24. Which statement is **NOT** true? #anonymousclass

- [ ] An anonymous class may specify an abstract base class as its base type.
- [ ] An anonymous class does not require a zero-argument constructor.
- [ ] An anonymous class may specify an interface as its base type.
- [ ] An anonymous class may specify both an abstract class and interface as base types.

> [!note] 
>  An anonymous class does not require a zero-argument constructor. is true


#### Q 25. What will this program print out to the console when executed? #linkedlist

```java

import java.util.LinkedList;


public class Main {

    public static void main(String[] args){

        LinkedList<Integer> list = new LinkedList<>();

        list.add(5);

        list.add(1);

        list.add(10);

        System.out.println(list);

    }

}

```

- [x] [5, 1, 10]
- [ ] [10, 5, 1]
- [ ] [1, 5, 10]
- [ ] [10, 1, 5]


#### Q 26. What is the output of this code? #exception 

```java

class Main {

    public static void main(String[] args){

       String message = "Hello";

       for (int i = 0; i<message.length(); i++){

          System.out.print(message.charAt(i+1));

       }

    }

}

```

- [ ] "Hello"
- [x] A runtime exception is thrown.
- [ ] The code does not compile.
- [ ] "ello"


#### Q 27. Object-oriented programming is a style of programming where you organize your program around \_ and data, rather than \_ and logic. #oop 

- [ ] functions; actions
- [x] objects; actions
- [ ] actions; functions
- [ ] actions; objects


#### Q 28. What statement returns true if "nifty" is of type String? #string 

- [ ] `"nifty".getType().equals("String")`
- [ ] `"nifty".getType() == String`
- [ ] `"nifty".getClass().getSimpleName() == "String"`
- [x] `"nifty" instanceof String`


#### Q 29. What is the output of this code? #list #primitivedatatype 

```java

import java.util.*;

class Main {

    public static void main(String[] args) {

        List<Boolean> list = new ArrayList<>();

        list.add(true);

        list.add(Boolean.parseBoolean("FalSe"));

        list.add(Boolean.TRUE);

        System.out.print(list.size());

        System.out.print(list.get(1) instanceof Boolean);

    }

}

```

- [ ] A runtime exception is thrown.
- [ ] 3 false
- [ ] 2 true
- [x] 3 true


#### Q 30. What is the result of this code? #class 

```java

1: class Main {

2:     Object message() {

3:         return "Hello!";

4:     }

5:     public static void main(String[] args) {

6:         System.out.print(new Main().message());

7:         System.out.print(new Main2().message());

8:     }

9: }

10: class Main2 extends Main {

11:     String message() {

12:         return "World!";

13:     }

14: }

```

- [ ] It will not compile because of line 7.
- [ ] Hello!Hello!
- [x] Hello!World!
- [ ] It will not compile because of line 11.


#### Q 31. What method can be used to create a new instance of an object? #class 

- [ ] another instance
- [ ] field
- [x] constructor
- [ ] private method


#### Q 32. Which is the most reliable expression for testing whether the values of two string variables are the same? #string 

- [ ] string 1 == string 2
- [ ] string 1 = string 2
- [ ] string 1.matches(string 2)
- [x] string 1.equals(string 2)


#### Q 33. Which letters will print when this code is run? #error

```java

public static void main(String[] args) {

    try {

        System.out.println("A");

        badMethod();

        System.out.println("B");

    } catch (Exception ex) {

        System.out.println("C");

    } finally {

        System.out.println("D");

    }

}

public static void badMethod() {

    throw new Error();

}

```

- [ ] A, B, and D
- [ ] A, C, and D
- [ ] C and D
- [x] A and D

> [!note] 
>  Error 不继承 Exception，二者共同继承于 Throwable 


#### Q 34. What is the output of this code? #class 

```java

class Main {

    static int count = 0;

    public static void main(String[] args) {

        if (count < 3) {

            count++;

            main(null);

        } else {

            return;

        }

        System.out.println("Hello World!");

    }

}

```

- [ ] It will throw a runtime exception.
- [ ] It will not compile.
- [x] It will print "Hello World!" three times.
- [ ] It will run forever.


#### Q 35. What is the output of this code? #list 

```java

import java.util.*;

class Main {
    public static void main(String[] args) {
        String[] array = {"abc", "2", "10", "0"};
        List<String> list = Arrays.asList(array);
        Collections.sort(list);
        System.out.println(Arrays.toString(array));
    }
}

```

- [ ] `[abc, 0, 2, 10]`
- [ ] The code does not compile.
- [ ] `[abc, 2, 10, 0]`
- [x] `[0, 10, 2, abc]`

> [!note] 
> 不同类型不能排序，字符串排序先数字再字母，一位一位相比较


#### Q 36. What is the output of this code? #class 

```java

class Main {

    public static void main(String[] args) {

        String message = "Hello";

        print(message);

        message += "World!";

        print(message);

    }

    static void print(String message) {

        System.out.print(message);

        message += " ";

    }

}

```

- [ ] Hello World!
- [x] HelloHelloWorld!
- [ ] Hello Hello World!
- [ ] Hello HelloWorld!


#### Q 37. What is displayed when this code is compiled and executed? #class 

```java

public class Main {

    public static void main(String[] args) {

        int x = 5;

        x = 10;

        System.out.println(x);

    }

}

```

- [ ] x
- [ ] null
- [x] 10
- [ ] 5


#### Q 38. Which approach ====cannot==== be used to iterate over a List named _theList_? #loop


- [ ] A

```java
for (int i = 0; i < theList.size(); i++) {
    System.out.println(theList.get(i));
}
```

- [ ] B

```java
for (Object object : theList) {
    System.out.println(object);
}
```

- [x] C

```java
Iterator it = theList.iterator();
for (it.hasNext()) {
    System.out.println(it.next());
}
```

- [ ] D

```java
theList.forEach(System.out::println);
```

> [!note] 
> **Explanation:** `for (it.hasNext())` should be `while (it.hasNext())`. 


#### Q 39. What method signature will work with this code? #class 

``` java
boolean healthyOrNot = isHealthy("avocado");
```

- [ ] public void isHealthy(String avocado)
- [x] boolean isHealthy(String string)
- [ ] public isHealthy("avocado")
- [ ] private String isHealthy(String food)


#### Q 40. Which are valid keywords in a Java module descriptor (module-info.java)? #module 

- [ ] provides, employs
- [ ] imports, exports
- [ ] consumes, supplies
- [x] requires, exports

> [!note] 
>  module 常见关键字

#### Q 41. Which type of variable keeps a constant value once it is assigned? #class 

- [ ] non-static
- [ ] static
- [x] final
- [ ] private


#### Q 42. How does the keyword `volatile` affect how a variable is handled? #keyword

- [ ] It will be read by only one thread at a time.
- [ ] It will be stored on the hard drive.
- [x] It will never be cached by the CPU.
- [ ] It will be preferentially garbage collected.


#### Q 43. What is the result of this code? #variable

```java
char smooch = 'x';
System.out.println((int) smooch);
```

- [ ] an alphanumeric character
- [ ] a negative number
- [x] a positive number
- [ ] a ClassCastException


#### Q 44. You get a `NullPointerException`. What is the most likely cause? #exception 

- [ ] A file that needs to be opened cannot be found. `FileNotFoundException`
- [ ] A network connection has been lost in the middle of communications. `IOException`
- [ ] Your code has used up all available memory. `OutOfMemoryError`
- [x] The object you are using has not been instantiated. 


#### Q 45. How would you fix this code so that it compiles? #class 

```java

public class Nosey {

    int age;

    public static void main(String[] args) {

        System.out.println("Your age is: " + age);

    }

}

```

- [x] Make age static.
- [ ] Make age global.
- [ ] Make age public.
- [ ] Initialize age to a number.


#### Q 46. Add a Duck called "Waddles" to the `ArrayList` **ducks**. #arraylist 

```java

public class Duck {

    private String name;

    Duck(String name) {}

}

```

- [ ] `Duck waddles = new Duck();`
      `ducks.add(waddles);`
- [ ] `Duck duck = new Duck("Waddles");`
      `ducks.add(waddles);`
- [x] `ducks.add(new Duck("Waddles"));`
- [ ] `ducks.add(new Waddles());`


#### Q 47. If you encounter `UnsupportedClassVersionError` it means the code was `___` on a newer version of Java than the JRE `___` it. #exception 

- [ ] executed; interpreting
- [ ] executed; compiling
- [x] compiled; executing
- [ ] compiled, translating


#### Q 48. Given this class, how would you make the code compile? #keyword

```java

public class TheClass {

    private final int x;

}

```

- [ ] A

```java

public TheClass() {

    x += 77;

}

```

- [ ] B

```java

public TheClass() {

    x = null;

}

```

- [x] C

```java

public TheClass() {

    x = 77;

}

```

- [ ] D

```java

private void setX(int x) {

    this.x = x;

}

public TheClass() {

    setX(77);

}

```


#### Q 49. How many times f will be printed? #loop 

```java

public class Solution {

    public static void main(String[] args) {

        for (int i = 44; i > 40; i--) {

            System.out.println("f");

        }

    }

}

```

- [x] 4
- [ ] 3
- [ ] 5
- [ ] A Runtime exception will be thrown


#### Q 50. Which statements about `abstract` classes are true? #class 

```

1. They can be instantiated.

2. They allow member variables and methods to be inherited by subclasses.

3. They can contain constructors.

```

- [ ] 1, 2, and 3
- [ ] only 3
- [x] 2 and 3
- [ ] only 2
