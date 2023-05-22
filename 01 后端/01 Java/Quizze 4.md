
https://github.com/Ebazhanov/linkedin-skill-assessments-quizzes/blob/main/java/java-quiz.md

#### Q 151. `void accept(T t)` is method of -?

- [x] Consumer
- [ ] Producer
- [ ] Both
- [ ] None

> [!note] 
>  

#### Q 152. Which of these does `Stream filter()` operates on?

- [x] Predicate
- [ ] Interface
- [ ] Class
- [ ] Methods
> [!note] 
>  

#### Q 153. Which of these does `Stream map()` operates on?

- [ ] Class
- [ ] Interface
- [ ] Predicate
- [x] Function
> [!note] 
>  

#### Q 154. What code is needed at line 8?


```java

1: class Main {


2:      public static void main(String[] args) {


3:          Map<String, Integer> map = new HashMap<>();

4:          map.put("a", 1);

5:          map.put("b", 2);

6:          map.put("c", 3);


7:          int result = 0;


8:

9:              result += entry.getValue();

10:         }


11:         System.out.println(result); // outputs 6

12:     }

13: }

```

- [ ] for(MapEntry<String, Integer> entry: map.entrySet()) {
- [ ] for(String entry: map) {
- [ ] for(Integer entry: map.values()) {
- [x] for(Entry<String, Integer> entry: map.entrySet()) {


#### Q 155. What will print when Lambo is instantiated?


```java

class Car {

    String color = "blue";

}


class Lambo extends Car {

    String color = "white";


    public Lambo() {

        System.out.println(super.color);

        System.out.println(this.color);

        System.out.println(color);

    }

}

```

- [x] blue

      white

      white
- [ ] blue

      white

      blue
- [ ] white

      white

      white
- [ ] white

      white

      blue


### Q 156. Which command will run a FrogSounds app that someone emailed to you as a jar?

- [ ] jar FrogSounds.java
- [ ] javac FrogSounds.exe
- [ ] jar cf FrogSounds.jar
- [x] java -jar FrogSounds.jar

> [!note] 
>  
#### Q 157. What is the default value of short variable?

- [x] 0
- [ ] 0.0
- [ ] null
- [ ] undefined


#### Q 158. What will be the output of the following Java program?


```java

class variable_scope {

    public static void main(String args[]) {

        int x;

        x = 5;

        {

            int y = 6;

            System.out.print(x + " " + y);

        }

        System.out.println(x + " " + y);

    }

}

```

- [x] Compilation Error
- [ ] Runtime Error
- [ ] 5 6 5 6
- [ ] 5 6 5


**Explanation:** Scope of variable Y is limited.


#### Q 159. Subclasses of an abstract class are created using the keyword **\_**.

- [x] extends
- [ ] abstracts
- [ ] interfaces
- [ ] implements


[Reference](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html)


#### Q 160. What will be the output of the following program?


```java

import java.util.Formatter;

public class Course {

    public static void main(String[] args) {

        Formatter data = new Formatter();

        data.format("course %s", "java ");

        System.out.println(data);

        data.format("tutorial %s", "Merit campus");

        System.out.println(data);

    }

}

```

- [ ] course java

      tutorial Merit campus
- [x] course java

      course java tutorial Merit campus
- [ ] Compilation Error
- [ ] Runtime Error
> [!note] 
>  

#### Q 161. Calculate the time complexity of the following program.

void printUnorderedPairs(int[] arrayA, int[] arrayB){
    for(int i = 0; i < arrayA.length; i++){
        for(int  j = 0; j < arrayB.length; j++){
            if(arrayA[i] < arrayB[j]){
                System.out.println(arrayA[i] + "," + arrayB[j]);
            }
        }
    }
 }
- [x] O(N\*N)
- [ ] O(1)
- [ ] O(AB)
- [ ] O(A\*B)

> [!note] 
>  

#### Q 162. What do these expressions evaluate to?


    1. true && false

    2. true && false || true

- [x] 1. false 2. true
- [ ] 1. false 2. false
- [ ] 1. true 2. false
- [ ] 1. true 2. true
