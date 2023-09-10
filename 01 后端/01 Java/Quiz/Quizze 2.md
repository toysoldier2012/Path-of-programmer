
https://github.com/Ebazhanov/linkedin-skill-assessments-quizzes/blob/main/java/java-quiz.md

#### Q 51. Which keyword lets you call the constructor of a parent class?

- [ ] parent
- [x] super
- [ ] this
- [ ] new


#### Q 52. What is the result of this code?


```java

  1: int a = 1;

  2: int b = 0;

  3: int c = a/b;

  4: System.out.println(c);

```

- [x] It will throw an ArithmeticException.
- [ ] It will run and output 0.
- [ ] It will not compile because of line 3.
- [ ] It will run and output infinity.


#### Q 53. Normally, to access a static member of a class such as Math.PI, you would need to specify the class "Math". What would be the best way to allow you to use simply "PI" in your code?

- [x] Add a static import.
- [ ] Declare local copies of the constant in your code.
- [ ] This cannot be done. You must always qualify references to static members with the class form which they came from.
- [ ] Put the static members in an interface and inherit from that interface.


#### Q 54. Which keyword lets you use an interface?

- [ ] extends
- [x] implements
- [ ] inherits
- [ ] import


#### Q 55. Why are ArrayLists better than arrays?

- [x] You don't have to decide the size of an ArrayList when you first make it.
- [ ] You can put more items into an ArrayList than into an array.
- [ ] ArrayLists can hold more kinds of objects than arrays.
- [ ] You don't have to decide the type of an ArrayList when you first make it.


#### Q 56. Declare a variable that holds the first four digits of Π

- [ ] int pi = 3.141;
- [ ] decimal pi = 3.141;
- [x] double pi = 3.141;
- [ ] float pi = 3.141;

> [!note] 
> **Reasoning:**
> 
The default Java type which Java will be using for a float variable will be double.
So, even if you declare any variable as float, what the compiler has to actually do is to assign a double value to a float variable,
which is not possible. So, to tell the compiler to treat this value as a float, that 'F' is used. 

```java

public class TestReal {

    public static void main (String[] argv)

    {

      double pi = 3.14159265;       //accuracy up to 15 digits

      float pi 2 = 3.141 F;           //accuracy up to 6-7 digits


      System.out.println ("Pi=" + pi);

      System.out.println ("Pi 2=" + pi 2);

    }

  }

```


#### Q 57. Use the magic power to cast a spell

```java

public class MagicPower {

    void castSpell(String spell) {}

}

```

- [x] `new MagicPower().castSpell("expecto patronum");`
- [ ] `MagicPower magicPower = new MagicPower();`
      `magicPower.castSpell();`
- [ ] `MagicPower.castSpell("expelliarmus");`
- [ ] `new MagicPower.castSpell();`


#### Q 58. What language construct serves as a blueprint containing an object's properties and functionality?

- [ ] constructor
- [ ] instance
- [x] class
- [ ] method


#### Q 59. What does this code print?

```java

public static void main(String[] args) {

    int x=5,y=10;

    swapsies(x,y);

    System.out.println(x+" "+y);

}


static void swapsies(int a, int b) {

    int temp=a;

    a=b;

    b=temp;

}

```

- [ ] 10 10
- [x] 5 10
- [ ] 10 5
- [ ] 5 5

> [!note] 
>  

#### Q 60. What is the result of this code?


```java

try {

    System.out.println("Hello World");

} catch (Exception e) {

    System.out.println("e");

} catch (ArithmeticException e) {

    System.out.println("e");

} finally {

    System.out.println("!");

}

```

- [ ] Hello World
- [x] It will not compile because the second catch statement is unreachable
- [ ] Hello World!
- [ ] It will throw runtime exception


#### Q 61. Which is not a java keyword

- [ ] finally
- [ ] native
- [ ] interface
- [x] unsigned


#### Q 62. Which operator would you use to find the remainder after division?

- [x] `%`
- [ ] `//`
- [ ] `/`
- [ ] `DIV`


[Reference](http://www.cs.ukzn.ac.za/~hughm/java/intro/week2/21.html)


#### Q 63. Which choice is a disadvantage of inheritance?

- [ ] Overridden methods of the parent class cannot be reused.
- [x] Responsibilities are not evenly distributed between parent and child classes.
- [ ] Classes related by inheritance are tightly coupled to each other.
- [ ] The internal state of the parent class is accessible to its children.

[Reference](http://erpbasic.blogspot.com/2012/01/inheritance-advantages-and.html#:~:text=Main%20disadvantage%20of%20using%20inheritance,used%20independent%20of%20each%20other.&text=4.,case%20of%20using%20that%20method.)

#### Q 64. How would you declare and initialize an array of 10 ints?

- [ ] `Array<Integer> numbers = new Array<Integer>(10);`
- [ ] `Array[int] numbers = new Array [int](10);`
- [x] `int[] numbers = new int[10];`
- [ ] `int numbers[] = int[10];`


#### Q 65. Refactor this event handler to a lambda expression:


```java

groucyButton.addActionListener(new ActionListener() {

    @Override

    public void actionPerformed(ActionEvent e) {

        System.out.println("Press me one more time..");

    }

});

```

- [ ] `groucyButton.addActionListener(ActionListener listener -> System.out.println("Press me one more time..."));`
- [x] `groucyButton.addActionListener((event) -> System.out.println("Press me one more time..."));`
- [ ] `groucyButton.addActionListener(new ActionListener(ActionEvent e) {() -> System.out.println("Press me one more time...");});`
- [ ] `groucyButton.addActionListener(() -> System.out.println("Press me one more time..."));`


[Reference](https://www.codejava.net/java-core/the-java-language/java-8-lambda-listener-example)


#### Q 66. Which functional interfaces does Java provide to serve as data types for lambda expressions?

- [ ] Observer, Observable
- [ ] Collector, Builder
- [ ] Filter, Map, Reduce
- [x] Consumer, Predicate, Supplier

[Reference](https://www.baeldung.com/java-8-functional-interfaces)


#### Q 67. What is a valid use of the hashCode() method?

- [ ] encrypting user passwords
- [ ] deciding if two instances of a class are equal
- [x] enabling HashMap to find matches faster
- [ ] moving objects from a List to a HashMap

#### Q 68. What kind of relationship does "extends" denote?

- [ ] uses-a
- [x] is-a
- [ ] has-a
- [ ] was-a


[Reference](https://www.c-sharpcorner.com/UploadFile/3614a6/is-a-and-has-a-relationship-in-java/)


#### Q 69. How do you force an object to be garbage collected?

- [ ] Set object to null and call Runtime.gc()
- [x] Set object to null and call System.gc()
- [ ] Set object to null and call Runtime.getRuntime().runFinalization()
- [ ] There is no way to force an object to be garbage collected


[Reference](https://sematext.com/blog/java-garbage-collection/)


#### Q 70. Java programmers commonly use design patterns. Some examples are the **\_**, which helps create instances of a class, the **\_**, which ensures that only one instance of a class can be created; and the **\_**, which allows for a group of algorithms to be interchangeable. #pattern

- [x] static factory method; singleton; strategy pattern
- [ ] strategy pattern; static factory method; singleton
- [ ] creation pattern; singleton; prototype pattern
- [ ] singleton; strategy pattern; static factory method

> [!note] 
> 复习一下其他设计模式
> 


#### Q 71. Using Java's Reflection API, you can use \_ to get the name of a class and \_ to retrieve an array of its methods.

- [x] this.getClass().getSimpleName(); this.getClass().getDeclaredMethods()
- [ ] this.getName(); this.getMethods()
- [ ] Reflection.getName(this); Reflection.getMethods(this)
- [ ] Reflection.getClass(this).getName(); Reflection.getClass(this).getMethods()


#### Q 72. Which is not a valid lambda expression? #lambda

- [ ] `a -> false;`
- [ ] `(a) -> false;`
- [x] `String a -> false;`
- [ ] `(String a) -> false;`

> [!note] 
>  
#### Q 73. Which access modifier makes variables and methods visible only in the class where they are declared?

- [ ] public
- [ ] protected
- [ ] nonmodifier
- [x] private


#### Q 74. What type of variable can be assigned to only once?

- [ ] private
- [ ] non-static
- [x] final
- [ ] static

#### Q 75. How would you convert a String to an Int?

- [ ] `"21".intValue()`
- [ ] `String.toInt("21")`
- [x] `Integer.parseInt("21")`
- [ ] `String.valueOf("21")`


#### Q 76. What method should be added to the Duck class to print the name Moby?

```java

public class Duck {

    private String name;


    Duck(String name) {

        this.name = name;

    }


    public static void main(String[] args) {

        System.out.println(new Duck("Moby"));

    }

}

```

- [x] `public String toString() { return name; } `
- [ ] `public void println() { System.out.println(name); } `
- [ ] `String toString() { return this.name; } `
- [ ] `public void toString() { System.out.println(this.name); } `


#### Q 77. Which operator is used to concatenate Strings in Java

- [x] `+`
- [ ] `&`
- [ ] `.`
- [ ] `-`


[Reference](https://www.techiedelight.com/concatenate-two-strings-java/)


#### Q 79. What is the value of myCharacter after line 3 is run?


```java

1: public class Main {

2:   public static void main (String[] args) {

3:     char myCharacter = "piper".charAt(3);

4:   }

5: }

```

- [ ] p
- [ ] r
- [x] e
- [ ] i

#### Q 80. When should you use a static method?

- [ ] when your method is related to the object's characteristics
- [x] when you want your method to be available independently of class instances
- [ ] when your method uses an object's instance variable
- [ ] when your method is dependent on the specific instance that calls it


#### Q 81. What phrase indicates that a function receives a copy of each argument passed to it rather than a reference to the objects themselves?

- [ ] pass by reference
- [ ] pass by occurrence
- [x] pass by value
- [ ] API call

> [!note] 
>  

#### Q 82. In Java, what is the scope of a method's argument or parameter?

- [x] inside the method
- [ ] both inside and outside the method
- [ ] neither inside nor outside the method
- [ ] outside the method


#### Q 83. What is the output of this code?


```java

public class Main {

  public static void main (String[] args) {

    int[] sampleNumbers = {8, 5, 3, 1};

    System.out.println(sampleNumbers[2]);

  }

}

```

- [ ] 5
- [ ] 8
- [ ] 1
- [x] 3


#### Q 84. Which change will make this code compile successfully?


```java

1: public class Main {

2:   String MESSAGE ="Hello!";

3:   static void print(){

4:     System.out.println(message);

5:   }

6:   void print2(){}

7: }

```

- [ ] Change line 2 to `public static final String message`
- [ ] Change line 6 to `public void print2(){}`
- [ ] Remove the body of the `print2` method and add a semicolon.
- [x] Remove the body of the `print` method.


#### Q 85. What is the output of this code? #list 


```java

import java.util.*;

class Main {

  public static void main(String[] args) {

    String[] array = new String[]{"A", "B", "C"};

    List<String> list1 = Arrays.asList(array);

    List<String> list2 = new ArrayList<>(Arrays.asList(array));

    List<String> list3 = new ArrayList<>(Arrays.asList("A", new String("B"), "C"));

    System.out.print(list1.equals(list2));

    System.out.print(list1.equals(list3));

  }

}

```

- [ ] falsefalse
- [x] truetrue
- [ ] falsetrue
- [ ] truefalse

> [!note] 
>  

#### Q 86. Which code snippet is valid?

- [ ] `ArrayList<String> words = new ArrayList<String>(){"Hello", "World"};`
- [ ] `ArrayList words = Arrays.asList("Hello", "World");`
- [ ] `ArrayList<String> words = {"Hello", "World"};`
- [x] `ArrayList<String> words = new ArrayList<>(Arrays.asList("Hello", "World"));`


#### Q 87. What is the output of this code?


```java

class Main {

  public static void main(String[] args) {

    StringBuilder sb = new StringBuilder("hello");

    sb.deleteCharAt(0).insert(0, "H")." World!";

    System.out.println(sb);

  }

}

```

- [x] It will not compile.
- [ ] "Hello World!"
- [ ] "hello"
- [ ] ????


#### Q 88. How would you use the TaxCalculator to determine the amount of tax on $50?


```java

class TaxCalculator {

  static double calculate(total) {

    return total * .05;

  }

}

```

- [x] TaxCalculator.calculate(50);
- [ ] new TaxCalculator.calculate(50);
- [ ] calculate(50);
- [ ] new TaxCalculator.calculate($50);


#### Q 89. Which characteristic does not apply to instances of java.util.HashSet?

- [ ] uses hashcode of objects when inserted
- [ ] contains unordred elements
- [ ] contains unique elements
- [x] contains sorted elements


#### Q 90. What is the output? #queue

```java

import java.util.*;


public class Main {

    public static void main(String[] args)

    {

        PriorityQueue<Integer> queue = new PriorityQueue<>();

        queue.add(4);

        queue.add(3);

        queue.add(2);

        queue.add(1);


        while (queue.isEmpty() == false) {

            System.out.printf("%d", queue.remove());

        }

    }

}

```

- [ ] 1 3 2 4
- [ ] 4 2 3 1
- [x] 1 2 3 4
- [ ] 4 3 2 1

> [!note] 
>  PriorityQueue 按照大小重排了数字

#### Q 91. What will this code print, assuming it is inside the main method of a class?


`System.out.println("hello my friends".split(" ")[0]);`

- [ ] my
- [ ] hellomyfriends
- [x] hello
- [ ] friends


#### Q92. You have an instance of type Map<String, Integer> named instruments containing the following key-value pairs: guitar=1200, cello=3000, and drum=2000. If you add the new key-value pair cello=4500 to the Map using the put method, how many elements do you have in the Map when you call instruments.size()?

- [ ] 2
- [ ] When calling the put method, Java will throw an exception
- [ ] 4
- [x] 3


#### Q 93. Which class acts as root class for Java Exception hierarchy?

- [ ] Clonable
- [x] Throwable
- [ ] Object
- [ ] Serializable


#### Q 94. Which class does not implement the java.util.Collection interface?

- [ ] java.util.Vector
- [ ] java.util.ArrayList
- [ ] java.util.HashSet
- [x] java.util.HashMap


#### Q95. You have a variable of named `employees` of type `List<Employee>` containing multiple entries. The `Employee` type has a method `getName()` that returns the employee name. Which statement properly extracts a list of employee names?

- [ ] `employees.collect(employee -> employee.getName());`
- [ ] `employees.filter(Employee::getName).collect(Collectors.toUnmodifiableList());`
- [x] `employees.stream().map(Employee::getName).collect(Collectors.toList());`
- [ ] `employees.stream().collect((e) -> e.getName());`

> [!note] 
> 


#### Q 96. This code does not compile. What needs to be changed so that it does?


```java

public enum Direction {

    EAST("E"),

    WEST("W"),

    NORTH("N"),

    SOUTH("S");


    private final String shortCode;


    public String getShortCode() {

        return shortCode;

    }

}

```

- [x] Add a constructor that accepts a `String` parameter and assigns it to the field `shortCode`.
- [ ] Remove the `final` keyword for the field `shortCode`.
- [ ] All enums need to be defined on a single line of code.
- [ ] Add a setter method for the field `shortCode`.


#### Q97. Which language feature ensures that objects implementing the `AutoCloseable` interface are closed when it completes?

- [ ] try-catch-finally
- [ ] try-finally-close
- [x] try-with-resources
- [ ] try-catch-close


#### Q 98. What code should go in line 3?

```java

1: class Main {

2:     public static void main(String[] args) {

3:

4:         array[0] = new int[]{1, 2, 3};

5:         array[1] = new int[]{4, 5, 6};

6:         array[2] = new int[]{7, 8, 9};

7:         for (int i = 0; i < 3; i++)

8:             System.out.print(array[i][1]); //prints 258

9:     }

10: }

```

- [ ] `int[][] array = new int[][];`
- [x] `int[][] array = new int[3][3];`
- [ ] `int[][] array = new int[2][2];`
- [ ] `int[][] array = [][];`


#### Q 99. Is this an example of method overloading or overriding? #override


```java

class Car {

    public void accelerate() {}

}

class Lambo extends Car {

    public void accelerate(int speedLimit) {}

    public void accelerate() {}

}

```

- [ ] neither
- [ ] both
- [x] overloading
- [ ] overriding
> [!note] 
>  

#### Q 100. Which choice is the best data type for working with money in Java?

- [ ] float
- [ ] String
- [ ] double
- [x] BigDecimal


[Reference](https://www.scaler.com/topics/java/primitive-data-types/#types-of-primitive-data-types-in-java)
