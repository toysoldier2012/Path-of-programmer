
https://welovedevs.com/app/fr/test-session/-NNxW7D1t9leA1jctqCd/results

#### Given this code : #static

```java
public class QuestionJava {
     
    String var = "we";
     
    public static void main(String[] data) {
        String var2 = "lovedev";
        System.out.print(var + var2);
    }
}
```

What will this code do ?

- [x] It doesn't compile.
- [ ] It compiles but throws an exception at runtime.
- [ ] It compiles and displays 5.
- [ ] It compiles and displays 15.

#### By convention, how should a package be named? #package

- [ ] All uppercase
- [ ] 1 st letter uppercase
- [ ] 1 st letter in lowercase and the first letter of a new word in uppercase
- [x] All lowercase

#### @BeforeTest is executed before each test? #TestNG #BeforeTest

- [x] True
- [ ] False

> [!note] 
>  

#### Are arrays primitives types in Java? #type

- [ ] Yes
- [x] No

#### Given this code, What will be displayed in the console? #operator

```java
public static void main(String[] args){
    int a = 2;
    a + = 2;
    System.out.println(a% 2);
}
```


- [ ] "4"
- [ ] "2"
- [x] "0"
- [ ] An error

> [!note] 
>  %求余 /除法，向下取整

#### Given this code, What will be displayed ? #array

```java
import java.util.ArrayList;
import java.util.List;
public class ArrayListQuestion {
public static void main(String[] args)
{
   List<String> list = new ArrayList<String>();
    list.add("Dhanbad");
    list.add(0, "New York");
    list.add("Mumbai");
    list.add(2, "Sydney");
    System.out.println(list);
  }
}
```

- [x] [New York, Dhanbad, Sydney, Mumbai]
- [ ] [Dhanbad, New York, Sydney, Mumbai]
- [ ] [Dhanbad, New York, Mumbai, Sydney]
- [ ] [New York, Dhanbad, Mumbai, Sydney]

#### How to handle an exception in JAVA? #exception

- [x] try{} catch{} throws{}
- [ ] new Exception()
- [ ] try{} get{}
- [ ] Object.exception()

#### Which of the following is/are a valid code comment in Java? #comment

- [x] `// this is a comment`
- [x] `/* this is a comment****/`
- [x] `/*** this is a comment***/`
- [ ] `# this is a comment`

> [!note] 
>  多写几个星号……也不是不行

#### What term should we use to call an interface in our java class? #interface

- [ ] Abstract
- [ ] Call
- [x] Implements
- [ ] Extends

#### Given this code, What should we modify at line 7 to display corretly the array and its elements? #array #arrays

```java
public class QuestionJava {
    public static void main(String[] args) {
        Integer[] tab = new Integer[3];
        tab[0] = 2;
        tab[1] = 5;
        tab[2] = 8;
        System.out.println(tab);
    }
}
```


- [ ] Array.toString(tab)
- [x] Arrays.toString(tab)
- [ ] "Tab.toString()"

> [!note] 
> Array 是数组，Arrays 是数组工具类

#### Which of the following operators is used to allocate memory for an object? #objet

- [ ] Give
- [x] New
- [ ] Alloc
- [ ] Malloc

#### What is java?

- [ ] A scripting programming language
- [x] An object-oriented programming language
- [ ] A variable oriented programming language

#### Enums cannot be declared: #enum 

- [ ] private
- [ ] public
- [ ] static
- [x] final

> [!note] 
>  枚举类作为内部类时，可以用 private 和 static 修饰

#### What is an IDE ?

- [ ] A tool for writing and running programs written in Java
- [x] An environment for developing programs
- [ ] A Java language instruction
- [ ] A website that allows you to reference the functionalities of a programming language

#### What keyword should be added so that the "nb_questions" attribute can be called without having to getter or instantiate a new class? #class

```java
private int nb_questions;
```

- [ ] final
- [ ] extends
- [x] static
- [ ] call

#### By convention, how should a new class be named? #class 

- [ ] javaQuizz
- [ ] JAVAQUIZZ
- [x] JavaQuizz

#### Which answer(s) declare a "string"array? #array 

- [x] String[] s
- [ ] string[] s
- [ ] String s[]
- [ ] String[s]

#### When we create a class without specifying the name of the package, its scope is : #class #visibility

- [x] Default
- [ ] Protected
- [ ] Public
- [ ] Private

#### How in a class, do we access its variables? #this

- [ ] the operator `:`
- [ ] the keyword `new`
- [x] the keyword `this`
- [ ] the operator `.`

#### How to concatenate two strings of characters? #string

- [x] "string 1"+"string 2"
- [ ] "string 1".."string 2"
- [x] "string 1"&&"string 2"
- [ ] "string 1"."string 2"

> [!note] 
> &&也可以连接字符串 

#### Which class should your unit test extend to make it a JUnit test? #junite

- [x] JUnitTest
- [ ] UnitTest
- [ ] JUnitCase
- [ ] TestCase

#### `--` is used for #operator 

- [ ] Remark
- [x] Decrement
- [ ] Substraction
- [ ] Negation

> [!note] 
>  Decrement -- Substraction - Negation !

#### What is “AssertEquals” used for in a Java Unit test? #junite 

- [x] It allows you to compare two objects
- [ ] It allows to differentiate two objects of the same type
- [ ] It allows you to check that an object as a parameter is equal to the second parameter

#### Which of the following annotations can you use in your JUnit test class? #junite 

- [ ] @Before, @After, @Test
- [x] @BeforeTest, @AfterTest
- [ ] @TestTest, @TestThis
- [ ] @TestClass, @TestMethod

#### What is the order of the variables in Enum? #enum 

- [ ] Descending order
- [ ] Ascending
- [ ] Random order
- [x] Depends on sort() method

#### Which of the following statements applies to methods of an interface in Java? #interface 

- [ ] An interface can only contain abstract methods.
- [x] You can define a method in an interface
- [ ] The private and protected access modifiers can also be used to declare methods in an interface
- [ ] Neither of the above is true.

> [!note] 
> 不能有 protected 方法 

#### Is a "HashMap" ordered? #hashmap 

- [ ] Yes
- [x] No

#### How to instantiate a new variable of type "integer"? #integer

- [x] int a = new Integer(3);
- [ ] int a = new int();
- [ ] int a = 4;
- [ ] Integer a = new int(5);

> [!note] 
>  int a = new Integer(3);过期了
>  int a = 4; 没有自动装箱，Integer i = 1 才是自动装箱

#### Does an ArrayList allow you to insert duplicate elements? #arraylist


- [x] Yes
- [ ] No

#### Given this code, What is displayed by the console? #string #stringbuilder

```java
public static void main(String[] args) {
          String str = "Automation";
          StringBuilder str2 = new StringBuilder();
          str2.append(str);
          str2 = str2.reverse();
         System.out.println(str2);
}
```

- [ ] Automating
- [x] noitamotuA
- [ ] the memory address of "str 2"
- [ ] A mistake


https://welovedevs.com/app/fr/test-session/-NTnpbl2tiF-EC_poSYQ/results

Au vu de cette interface, choisissez un nom plus approprié que "InterfaceANommer" :

![](https://process.filestackapi.com/output=quality:100/no_metadata/auto_image/compress/ZjMwUXIJSGiks6Vtsfn8)

TemperatureChangedBeanInfo

TemperatureChangedHelper

TemperatureChangedListener

TemperatureChangedFactory

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1832 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6N-YKp5Y_j4Zwb4/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

5

.

Parmi ces classes, laquelle est la plus appropriée pour composer une chaîne de caractère à partir de plusieurs éléments concaténés les uns aux autres ?

char[]

StringTokenizer

byte[]

StringBuilder

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1842 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NFTG2D8FlyCYuy/)

1

Evaluations de la communauté

8

.

Regardez la méthode suivante :

```java
private static Integer[] myCompute(int a) {  int i = 0;  Integer[] result = new Integer[2];  result[i++] = new Integer(a);  result[i] = new Integer(-a);  result[1 - i] = result[i];  return result;
}

```

Après l'appel:

```java
Integer[] call = myCompute(3);
```

Combien d'instances d'Integer ne peuvent pas être libérées de la mémoire ?

0

1

2

3

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1775 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NIo53nR94h8sek/)

1

Evaluations de la communauté

9

.

Au sujet des Thread, qu'est-il usuel de faire ?

Etendre la classe Thread et implémenter sa méthode run.

Etendre la classe Thread et implémenter sa méthode start.

Lancer le Thread en appelant sa méthode start.

Lancer le Thread en appelant sa méthode run.

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1854 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NLj6aBMMNghhLo/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

10

.

![](https://process.filestackapi.com/output=quality:100/no_metadata/auto_image/compress/GlP1uVqVS8eWHKbYhBmZ)

java.io.Readable

java.net.SocketReader

java.lang.Cloneable

java.io.Serializable

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1822 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NMhFiCD4jnFcRs/)

1

Evaluations de la communauté

14

.

Une ClassNotFoundException survient

Quand le ClassLoader ne trouve pas la classe demandée

Quand la définition de la classe demandée n’est pas trouvée

Quand une classe dépendante de la classe demandée n’est pas trouvée

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1873 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_Mm0AsbX8ENQCa/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

15

.

La visibilité d’une méthode peut être

private

override

protected

final

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1857 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_RgnCbFWlb8ZWE/)

2

Evaluations de la communauté

18

.

Une “garbage collection”

Alloue de la memoire aux objets créés

Supprime les objets non référencés

Peut être demandé par System.gc()

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1848 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_bFUQiI4F95QLH/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

19

.

En Java 11, le garbage collector par défaut est

G 1

Parallel GC

Serial GC

G 1 sauf pour les machines de petites tailles (1 CPU par exemple) où c'est le Serial GC

Auteur·ice: LoïcStatut : PubliéeQuestion passée 195 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/6e92a693-6a26-4835-b178-cc7d30eb5e9c/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

20

.

Si deux threads exécutent la méthode increment, après l'exécution par les 2 threads, la valeur de i sera

```java
private volatile int i;

public void increment() {  i++;
}
```

non prédictible

0

1

2

Auteur·ice: LoïcStatut : PubliéeQuestion passée 196 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/d7e318ef-7fb2-434e-92a1-b3fc2e1e51e4/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

#### Réponses incorrectes

1

.

A part java.lang.Object, y a-t-il une superclasse commune à Integer, Long, Byte, BigDecimal et Short ?

Oui, c'est java.lang.NumericValue.

Non, car BigDecimal n'est pas un type java standard.

Oui, c'est java.lang.Number.

Byte hérite de Short qui hérite de Integer qui hérite de Long, mais BigDecimal ne partage pas de superclasses communes avec ces types.

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1795 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6MaHeqPj2doF_OR/)

3

Evaluations de la communauté

3

.

Quel "design pattern" permet d'offrir un moyen de traiter les éléments d'un arbre sans se soucier du parcours ?

Decorator

TreeParser

Visitor

Observer

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1811 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6N8ZiPK5JLEFrni/)

2

Evaluations de la communauté

4

.

En ce qui concerne "InputStream", quelles propositions sont vraies parmi les suivantes :

Elle est définie dans java.io.

C'est une interface.

Elle est définie dans java.lang.

C'est une classe abstraite.

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1784 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NBBuY0Pdrt_nUj/)

1

Evaluations de la communauté

6

.

Regardez le code suivant:

```java  int a = 3;  do {      if ((a++ % 5) == 0)          break;  } while (a++ < 15);
```

Combien de fois le test `"(a++ < 15)"` est-il évalué ?

1

2

3

15

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1908 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NGGEWdZ1WMD1Cn/)

2

Evaluations de la communauté

7

.

Parmi ces affirmations correspondant au langage Java, lesquelles sont vraies ?

Une classe Java doit être compilée pour être exécutée.

Une classe Java est interprétée lorsqu'elle est exécutée.

Le temps d'exécution d'une méthode Java est toujours prédictible à la milliseconde près.

La taille maximum d'une classe Java est de 4 Ko.

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1847 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NHvgxp8rSck7b-/)

1

Evaluations de la communauté

11

.

![](https://process.filestackapi.com/output=quality:100/no_metadata/auto_image/compress/38OACUuQ16VobIE064aW)

C'est une mauvaise idée de transformer UnknownHostException en IllegalArgumentException.

Il manque une méthode readObject().

Il manque une méthode hashCode().

Il ne faut pas utiliser "transient".

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1853 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6NShV8P6xN_lXh_/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

12

.

Java est un langage

compilé

typé

script

impératif

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1807 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_Kj_0piBxCvPdw/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

13

.

A quoi sert le classpath ?

A indiquer l’emplacement de l’exécutable javac

A spécifier où la jvm retrouvera les .class

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1876 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_LusqMrqAYHY9L/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

16

.

Une instance d’ArrayList

Est thread safe

Implémente java.util.List

Refuse null

A une taille fixe non dépassable

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1875 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_XDy-ehb00WbYV/)

0

Aucun commentaire de la communauté, évaluez la question pour être le premier !

17

.

Une instance de HashMap

Garantit l’ordre des pairs clé-valeur

Implémente java.util.Map

Est thread safe

Autorise les valeurs null

VOIR LA CORRECTION ![🔐](https://cdnjs.cloudflare.com/ajax/libs/twemoji/14.0.2/svg/1f510.svg)

Auteur·ice: Thomas De verdièreStatut : PubliéeQuestion passée 1856 fois

Modifier [Lien direct](https://welovedevs.com/app/fr/tests/-M4-8q311sNrl8ekEsrx/questions/-M4PV6_YTuhllx6HkbG2/)