
https://github.com/Ebazhanov/linkedin-skill-assessments-quizzes/blob/main/java/java-quiz.md

#### Q 101. Which statement about constructors is not true?

- [ ] A class can have multiple constructors with a different parameter list.
- [ ] You can call another constructor with `this` or `super`.
- [ ] A constructor does not define a return value.
- [x] Every class must explicitly define a constructor without parameters.


#### Q 102. What language feature allows types to be parameters on classes, interfaces, and methods in order to reuse the same code for different data types?

- [ ] Regular Expressions
- [ ] Reflection
- [x] Generics
- [ ] Concurrency


#### Q 103. What will be printed?


```java

public class Berries{


    String berry = "blue";


    public static void main(String[] args) {

        new Berries().juicy("straw");

    }

    void juicy(String berry){

        this.berry = "rasp";

        System.out.println(berry + "berry");

    }

}

```

- [ ] raspberry
- [x] strawberry
- [ ] blueberry
- [ ] rasp


#### Q104. What is the value of `forestCount` after this code executes?


```java

Map<String, Integer> forestSpecies = new HashMap<>();


forestSpecies.put("Amazon", 30000);

forestSpecies.put("Congo", 10000);

forestSpecies.put("Daintree", 15000);

forestSpecies.put("Amazon", 40000);


int forestCount = forestSpecies.size();

```

- [x] 3
- [ ] 4
- [ ] 2
- [ ] When calling the put method, Java will throw an exception


#### Q 105. What is a problem with this code?

```java

import java.util.ArrayList;

import java.util.Arrays;

import java.util.List;


class Main {


    public static void main(String[] args) {

        List<String> list = new ArrayList<String>(Arrays.asList("a", "b", "c"));

        for(String value :list) {

            if(value.equals("a")) {

                list.remove(value);

            }

        }

        System.out.println(list); // outputs [b,c]

    }

}

```

- [ ] String should be compared using == method instead of equals.
- [x] Modifying a collection while iterating through it can throw a ConcurrentModificationException.
- [ ] The List interface does not allow an argument of type String to be passed to the remove method.
- [ ] ArrayList does not implement the List interface.

> [!note] 
>  foreach 不能删除

#### Q 106. How do you convert this method into a lambda expression?


```java

public int square(int x) {

    return x * x;

}

```

- [ ] `Function<Integer, Integer> squareLambda = (int x) -> { x * x };`
- [ ] `Function<Integer, Integer> squareLambda = () -> { return x * x };`
- [x] `Function<Integer, Integer> squareLambda = x -> x * x;`
- [ ] `Function<Integer, Integer> squareLambda = x -> return x * x;`


#### Q 107. Which choice is a valid implementation of this interface?


```java

interface MyInterface {

    int foo(int x);

}

```

- [ ] A


```java

public class MyClass implements MyInterface {

    // ....

    public void foo(int x){

        System.out.println(x);

    }

}

```

- [ ] B


```java

public class MyClass implements MyInterface {

    // ....

    public double foo(int x){

        return x * 100;

    }

}

```

- [x] C


```java

public class MyClass implements MyInterface {

    // ....

    public int foo(int x){

        return x * 100;

    }

}

```

- [ ] D


```java

public class MyClass implements MyInterface {

    // ....

    public int foo(){

        return 100;

    }

}

```


#### Q 108. What is the result of this program?

```java

interface Foo {

    int x = 10;

}


public class Main{


    public static void main(String[] args) {

        Foo.x = 20;

        System.out.println(Foo.x);

    }

}

```

- [ ] 10
- [ ] 20
- [ ] null
- [x] An error will occur when compiling.


#### Q 109. Which statement must be inserted on line 1 to print the value true?


```java

1:

2: Optional<String> opt = Optional.of(val);

3: System.out.println(opt.isPresent());

```

- [ ] `Integer val = 15;`
- [x] `String val = "Sam";`
- [ ] `String val = null;`
- [ ] `Optional<String> val = Optional.empty();`


#### Q 110. What will this code print, assuming it is inside the main method of a class?


```java

System.out.println(true && false || true);

System.out.println(false || false && true);

```

- [ ] false </br> true
- [ ] true </br> true
- [x] true </br> false
- [ ] false </br> false


#### Q 111. What will this code print? #list 


```java

List<String> list1 = new ArrayList<>();

list1.add("One");

list1.add("Two");

list1.add("Three");


List<String> list2 = new ArrayList<>();

list2.add("Two");


list1.remove(list2);

System.out.println(list1);

```

- [ ] `[Two]`
- [x] `[One, Two, Three]`
- [ ] `[One, Three]`
- [ ] `Two`
> [!note] 
>  

#### Q112. Which code checks whether the characters in two Strings,named `time` and `money`, are the same?

- [ ] `if(time <> money){}`
- [x] `if(time.equals(money)){}`
- [ ] `if(time == money){}`
- [ ] `if(time = money){}`


#### Q 113. An **\_** is a serious issue thrown by the JVM that the JVM is unlikely to recover from. An **\_** is an unexpected event that an application may be able to deal with in order to continue execution.

- [ ] exception,assertion
- [ ] AbnormalException, AccidentalException
- [x] error, exception
- [ ] exception, error


#### Q 114. Which keyword would not be allowed here?

```java

class Unicorn {

    _____ Unicorn(){}

}

```

- [x] static
- [ ] protected
- [ ] public
- [ ] void


#### Q 115. Which OOP concept is this code an example of?


```java

List[] myLists = {

    new ArrayList<>(),

    new LinkedList<>(),

    new Stack<>(),

    new Vector<>(),

};


for (List list : myLists){

    list.clear();

}

```

- [ ] composition
- [ ] generics
- [x] polymorphism
- [ ] encapsulation


**Explanation:** switch between different implementations of the `List` interface.


#### Q 116. What does this code print?


```java

String a = "bikini";

String b = new String("bikini");

String c = new String("bikini");


System.out.println(a == b);

System.out.println(b == c);

```

- [ ] true; false
- [x] false; false
- [ ] false; true
- [ ] true; true


**Explanation:** `== operator` compares the object reference. `String a = "bikini"; String b = "bikini";` would result in True. Here new creates a new object, so false. Use `equals() method` to compare the content.


#### Q 117. What keyword is added to a method declaration to ensure that two threads do not simultaneously execute it on the same object instance?

- [ ] native
- [ ] volatile
- [x] synchronized
- [ ] lock

[Reference](https://docs.oracle.com/javase/tutorial/essential/concurrency/syncmeth.html)
> [!note] 
> lock 不是关键字，是个接口 

#### Q 118. Which is a valid type for this lambda function?


```java

_____ oddOrEven = x -> {

    return x % 2 == 0 ? "even" : "odd";

};

```

- [ ] `Function<Integer, Boolean>`
- [ ] `Function<String>`
- [x] `Function<Integer, String>`
- [ ] `Function<Integer>`

[Explaination](https://github.com/0nyr/java/tree/main/examples/lambda_function), [Reference](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/)


#### Q 119. What is displayed when this code is compiled and executed?


```java

import java.util.HashMap;


public class Main {

    public static void main(String[] args) {

        HashMap<String, Integer> pantry = new HashMap<>();


        pantry.put("Apples", 3);

        pantry.put("Oranges", 2);


        int currentApples = pantry.get("Apples");

        pantry.put("Apples", currentApples + 4);


        System.out.println(pantry.get("Apples"));

    }

}

```

- [ ] 6
- [ ] 3
- [ ] 4
- [x] 7


[Explanation](https://github.com/0nyr/java/tree/main/training/linkedin_assessment/what_is_displayed_0)


#### Q 120. What variable type should be declared for capitalize?


```shell

List<String> songTitles = Arrays.asList("humble", "element", "dna");

_______ capitalize = (str) -> str.toUpperCase();

songTitles.stream().map(capitalize).forEach(System.out::println);

```

- [x] `Function<String, String>`
- [ ] `Stream<String>`
- [ ] `String<String, String>`
- [ ] `Map<String, String>`

[Explanation](https://github.com/0nyr/java/tree/main/training/linkedin_assessment/what_variable_type_0), [Reference](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/)


#### Q 121. Which is the correct return type for the processFunction method?


```java

_____ processFunction(Integer number, Function<Integer, String> lambda) {

    return lambda.apply(number);

}

```

- [ ] `Integer`
- [x] `String`
- [ ] `Consumer`
- [ ] `Function<Integer, String>`

[Explanation](https://github.com/0nyr/java/tree/main/training/linkedin_assessment/which_return_type_0)


#### Q 122. What function could you use to replace slashes for dashes in a list of dates?


```java

List<String> dates = new ArrayList<String>();

// missing code

dates.replaceAll(replaceSlashes);

```

- [x] `UnaryOperator<String> replaceSlashes = date -> date.replace("/", "-");`
- [ ] `Function<String, String> replaceSlashes = dates -> dates.replace("-", "/");`
- [ ] `Map<String, String> replaceSlashes = dates.replace("/", "-");`
- [ ] `Consumer<Date> replaceSlashes = date -> date.replace("/", "-");`

> [!note] 
> **Explanation:** `replaceAll` method for any `List<T>` only accepts `UnaryOperator<T>` to pass every single element into it then put the result into the `List<T>` again.




#### Q 123. From which class do all other classes implicitly extend?

- [x] `Object`
- [ ] `Main`
- [ ] `Java`
- [ ] `Class`


[Explanation](https://stackoverflow.com/questions/17187218/default-class-that-is-extended-by-all-classes-in-java)


#### Q 124. How do you create and run a Thread for this class?


```java

import java.util.date;


public class CurrentDateRunnable implements Runnable {

    @Override

    public void run () {

        while (true) {

            System.out.println("Current date: " + new Date());


            try {

                Thread.sleep(5000);

            } catch (InterruptedException e) {

                throw new RuntimeException(e);

            }

        }

    }

}

```

- [x] `Thread thread = new Thread(new CurrentDateRunnable()); thread.start();`
- [ ] `new Thread(new CurrentDateRunnable()).join();`
- [ ] `new CurrentDateRunnable().run();`
- [ ] `new CurrentDateRunnable().start();`


[Reference](https://www.w3schools.com/java/java_threads.asp)


#### Q 125. Which expression is a functional equivalent?


```java

List<Integer> numbers = List.of(1,2,3,4);

int total = 0;


for (Integer x : numbers) {

    if (x % 2 == 0)

    total += x * x;

}

```

- [ ] A


```java

int total = numbers.stream()

                        .transform(x -> x * x)

                        .filter(x -> x % 2 == 0)

                        .sum ();

```

- [ ] B


```java

int total = numbers.stream()

                        .filter(x -> x % 2 == 0)

                        .collect(Collectors.toInt());

```

- [ ] C


```java

int total = numbers.stream()

                        .mapToInt (x -> {if (x % 2 == 0) return x * x;})

                        .sum();

```

- [x] D


```java

int total = numbers.stream()

                        .filter(x -> x % 2 == 0)

                        .mapToInt(x -> x * x)

                        .sum();

```


**Explanation:** The given code in the question will give you the output 20 as total:


```java

numbers                         // Input `List<Integer>` > [1, 2, 3, 4]

    .stream()                   // Converts input into `Stream<Integer>`

    .filter(x -> x % 2 == 0)    // Filter even numbers and return `Stream<Integer>` > [2, 4]

    .mapToInt(x -> x * x)       // Square the number, converts `Integer` to an `int`, and returns `IntStream` > [4, 16]

    .sum()                      // Returns the sum as `int` > 20

```


#### Q 126. Which is not one of the standard input/output streams provided by java.lang.System?

- [x] print
- [ ] out
- [ ] err
- [ ] in


#### Q 127. The compiler is complaining about this assignment of the variable pickle to the variable jar. How woulld you fix this?


```java

double pickle = 2;

int jar = pickle;

```

- [ ] Use the method toInt() to convert pickle before assigning it to jar.
- [x] Cast pickle to an int before assigning it to jar.
- [ ] Make pickle into a double by adding + ".0"
- [ ] Use the new keyword to create a new Integer from pickle before assigning it to jar.


[Reference](https://www.w3schools.com/java/java_type_casting.asp)


#### Q 128. What value should x have to make this loop execute 10 times?


```java

for(int i=0; i<30; i+=x) {}

```

- [ ] 10
- [x] 3
- [ ] 1
- [ ] 0


#### Q 129. The **\_** runs compiled Java code, while the **\_** compiles Java files.

- [ ] IDE; JRE
- [ ] JDK; IDE
- [x] JRE; JDK
- [ ] JDK; JRE


[Reference](https://stackoverflow.com/questions/1906445/what-is-the-difference-between-jdk-and-jre)


#### Q 130. Which packages are part of Java Standard Edition #package 

- [ ] java.net
- [ ] java.util
- [ ] java.lang
- [x] All above

> [!note] 
>  

[Reference](https://docs.oracle.com/en/java/javase/11/docs/api/allpackages-index.html)


#### Q 131. What values for x and y will cause this code to print "btc"?


```java

String buy = "bitcoin";

System.out.println(buy.substring(x, x+1) + buy.substring(y, y+2))

```

- [x] int x = 0; int y = 2;
- [ ] int x = 1; int y = 3;
- [ ] int x = 0; int y = 3;
- [ ] int x = 1; int y = 3;


#### Q 132. Which keyword would you add to make this method the entry point of the program?

- [ ] exception
- [ ] args
- [x] static
- [ ] String


[Reference](https://www.geeksforgeeks.org/java-main-method-public-static-void-main-string-args/)


#### Q 133. You have a list of Bunny objects that you want to sort by weight using Collections.sort. What modification would you make to the Bunny class?

- [x] Implement the comparable interface by overriding the compareTo method.
- [ ] Add the keyword default to the weight variable.
- [ ] Override the equals method inside the Bunny class.
- [ ] Implement Sortable and override the sortBy method.

[Reference](https://www.geeksforgeeks.org/how-to-override-compareto-method-in-java/)


#### Q 134. Identify the incorrect Java feature.

- [ ] Object oriented
- [x] Use of pointers
- [ ] Dynamic
- [ ] Architectural neural


[Reference](https://www.interviewbit.com/blog/features-of-java/)


#### Q 135. What is the output of this code?


```java

int yearsMarried = 2;

switch (yearsMarried) {

   case 1:

      System.out.println("paper");

   case 2:

      System.out.println("cotton");

   case 3:

      System.out.println("leather");

   default:

      System.out.println("I don't gotta buy gifts for nobody!");

}

```

- [ ] cotton
- [ ] cotton <br> leather
- [x] cotton <br> leather <br> I don't gotta buy gifts for nobody!
- [ ] cotton <br> I don't gotta buy gifts for nobody!

> [!note] 
>  

[Reference](https://stackoverflow.com/a/8564008)


#### Q 136. What language feature do these expressions demonstrate?


```

System.out::println

Doggie::fetch

```

- [ ] condensed invocation
- [ ] static references
- [x] method references
- [ ] bad code


[Reference](https://stackoverflow.com/questions/31020269/what-is-the-use-of-system-outprintln-in-java-8)


#### Q 137. What is the difference between the wait() and sleep methods?

- [ ] Only Threads can wait, but any Object can be put to sleep.
- [ ] A wait can be woken up by another Thread calling notify whereas a sleep cannot.
- [ ] When things go wrong, sleep throws an IllegalMonitorStateException whereas wait throws an InterruptedException.
- [ ] Sleep allows for multi-threading whereas wait does not.


[Reference](https://docs.oracle.com/javase/tutorial/essential/concurrency/notify.html)


#### Q 138. Which is the right way to declare an enumeration of cats? #enum 

- [ ] enum Cats (SPHYNX, SIAMESE, BENGAL);
- [ ] enum Cats ("sphynx", "siamese", "bengal");
- [x] enum Cats {SPHYNX, SIAMESE, BENGAL}
- [ ] enum Cats {"sphynx","siamese","bengal}

#### Q 139. What happens when this code is run?


```java

List<String> horses = new ArrayList<String>();

horses.add (" Sea Biscuit ");

System.out.println(horses.get(1).trim());

```

- [ ] "Sea Biscuit" will be printed.
- [ ] " Sea Biscuit " will be printed.
- [x] An IndexOutOfBoundsException will be thrown.
- [ ] A NullPointerException will be thrown.


#### Q 140. Which data structure would you choose to associate the amount of rainfall with each month?

- [ ] Vector
- [ ] LinkedList
- [x] Map
- [ ] Queue


**Explanation:**


> from @yktsang01 in #3915 thread


Map because map is a key/value pair without creating new classes/objects. So can store the rainfall per month like `Map<java.time.Month, Double>`.

The other options will most likely need some new class to be meaningful:


```java

public class Rainfall {

    private java.time.Month month;

    private double rainfall;

}

Vector<Rainfall>

LinkedList<Rainfall>

Queue<Rainfall>

```


#### Q 141. Among the following which contains date information?

- [ ] java.sql timestamp
- [ ] java.io time
- [ ] java.io.timestamp
- [ ] java.sql.time

> [!note] 
>  -   java.sql timestamp: This option is correct. It is a class in the java.sql package that represents a SQL timestamp value, which includes both date and time information.
>  -   java.io time: This option is incorrect. There is no class called java.io time in Java.
>  -   java.io.timestamp: This option is incorrect. There is no class called java.io.timestamp in Java.
>  -   java.sql.time: This option is incorrect. It is a class in the java.sql package that represents a SQL time value, which includes only time information, not date information.


#### Q 142. What is the size of float and double in java?

- [x] 32 and 64
- [ ] 32 and 32
- [ ] 64 and 64
- [ ] 64 and 32

> [!note] 
>  int 也是 32 位

#### Q 143. When you pass an object reference as an argument to a method call what gets passed?

- [ ] a reference to a copy
- [x] a copy of the reference
- [ ] the object itself
- [ ] the original reference

> [!note] 
>  

#### Q 144. Which choice demonstrates a valid way to create a reference to a static function of another class?

- [x] Function<Integer, Integer> funcReference = MyClass::myFunction;
- [ ] Function<Integer, Integer> funcReference = MyClass.myFunction;
- [ ] Function<Integer, Integer> funcReference = MyClass().myFunction();
- [ ] Function<Integer, Integer> funcReference = MyClass::myFunction();


#### Q 145. What is UNICODE?

- [ ] Unicode is used for external representation of words and strings
- [ ] Unicode is used for internal representation of characters and strings
- [x] Unicode is used for external representation of characters and strings
- [ ] Unicode is used for internal representation of words and strings

> [!note] 
>  

#### Q 146. What kind of thread is the Garbage collector thread?

- [ ] User thread
- [x] Daemon thread
- [ ] Both
- [ ] None of these

> [!note] 
>  daemon thread 是守护线程，java 中另一个重要线程是用户线程 User thread

#### Q 147. What is HashMap and Map?

- [ ] HashMap is Interface and map is class that implements that
- [ ] HashMap is class and map is interface that implements that
- [ ] Map is class and Hashmap is interface that implements that
- [x] Map is Interface and Hashmap is class that implements that

#### Q 148. What invokes a thread's run() method?

- [ ] JVM invokes the thread's run() method when the thread is initially executed.
- [ ] Main application running the thread.
- [x] start() method of the thread class.
- [ ] None of the above.


**Explanation:** After a thread is started, via its `start()` method of the Thread class, the JVM invokes the thread's `run()` method when the thread is initially executed.


#### Q 149. What is true about a final class?

- [ ] class declared final is a final class.
- [ ] Final classes are created so the methods implemented by that class cannot be overriddden.
- [ ] It can't be inherited.
- [x] All of the above.

> [!note] 
>  

**Explanation:** Final classes are created so the methods implemented by that class cannot be overridden. It can't be inherited. These classes are declared `final`.


#### Q 150. Which method can be used to find the highest value of x and y?

- [ ] Math.largest(x,y)
- [ ] Math.maxNum(x,y)
- [x] Math.max(x,y)
- [ ] Math.maximum(x,y)
