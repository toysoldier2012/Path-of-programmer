# Les fondamentaux du langue objet 

> [!question] Pourquoi langage objet plutôt que langage procédurale ? #oop 
> - Certains caractères permet de faciliter le développement.
> - C'est une modélisation du monde réel, qui permet d'une représentation de concept complexe de manière plus naturelle 

> [!question] Les caractères de POO #oop 
> Il y en a trois principaux
> - Encapsulation est pour cacher les datas et les contenus sensitifs et aussi pour faciliter le développement.
> - Héritage et Polymorphisme augmente la réutilisabilité
> - On a deux type de polymorphisme, override et overload
> - Polymorphisme c'est à dire, Un instance peut avoir plusieurs forme, et pareil pour une méthode

> [!question] Couplage entre les objets? #oop #coupler 
> - Un couplage fort signifie que les classes et les objets dépendent les uns des autres. 
> - En général, le couplage fort n’est pas bon car il réduit la flexibilité et la stabilité du code 

> [!question] Quelles sont les différences entre class abstraite et interface #interface #abstract 
> - Les classes abstracts ne peuvent avoir que simple héritage, et les interface peuvent avoir multi héritage
> - Les classes abstracts peuvent avoir les constructeurs et les attributs
> - Dans les interfaces, tous les méthodes sont abstracts, après Java 8, les méthodes défaut et les méthodes statiques sont acceptés, après Java 9, privates et private statique sont acceptés
> - ==L'interface est une abstraction d'un comportement spécifique.==
> - ==La classe abstract est une abstraction d'un type de chose.== 

> [!question] Différence héritage et composition ? #heritage #composition 
> - L'héritage est un relation is-a
> - La composition est un relation has-some

> [!question] Peut-on Faire un override sur une méthode static ? #override #static 
Non, on peut pas réaliser le polymorphisme sur la méthode statique, cette dernière appartient une classe mais pas un objet 

> [!question] 子类的实现的抽象方法是在何时可以使用的？
> 
> 在 Java 中，子类实现父类的抽象方法可以在子类构造器执行完毕之后使用。这是因为在 Java 的对象创建过程中，构造器的执行是有顺序的，先执行父类的构造器，然后才执行子类的构造器。
> 当创建一个子类的实例时，以下顺序被遵循：
> 1. 分配对象内存空间。
> 2. 将对象内存空间初始化为零值（这就是为什么整型字段的默认值是 `0`）。
> 3. 设置对象的隐藏引用（即 Java 中的 `this`）。
> 4. 调用父类构造器。在这一步中，如果父类构造器调用了任何被子类覆盖的方法，那么将会执行子类中的版本。但是，如果这些方法依赖于子类构造器中初始化的任何状态，那么可能会导致问题，因为子类的成员变量尚未初始化。
> 5. 初始化子类成员变量和实例块（如果有的话）。
> 6. 执行子类构造器的其余部分。
> 
> 正因为此，在父类构造器中调用抽象方法是危险的，因为子类尚未完全构造好，调用的抽象方法可能会使用尚未初始化的变量，这可能会导致程序出现逻辑错误或运行时异常。
> 
> 因此，在子类的构造器完成之后，子类的方法（包括实现了父类抽象方法的那些方法）才可以被安全地使用，这时候可以保证所有的成员变量都已经被正确初始化。在代码中的最佳实践是避免在构造器中调用可以被覆盖的方法（非 `final` 方法），这样可以防止可能的错误或安全漏洞。

> [!question] 既然先执行父类的构造器，然后才执行子类的构造器，子类实现父类的抽象方法可以在子类构造器执行完毕之后使用，那么为什么在父类构造器中可以调用子类实现的抽象方法
> 
> 在 Java 中，即使是在父类构造器中，也可以调用子类实现的抽象方法。这是因为 Java 的动态绑定机制允许在运行时调用实际对象类型的方法。即便是在构造器中，如果一个方法是被子类覆盖的，那么无论它被父类构造器调用还是子类构造器调用，都会执行子类中的方法实现。
> 
> 然而，这是一个非常容易出错的操作，因为在父类构造器执行时，子类的成员变量还没有被初始化。如果覆盖的方法依赖于子类的状态（即依赖于子类的成员变量），这时这些成员变量可能还没有被赋予合适的初始值。
> 
> 这种设计可能会导致以下问题：
> - **方法依赖未初始化的状态**：如果子类覆盖的方法依赖于子类的成员变量，而这些变量还没有在子类的构造器中被初始化，那么方法可能会访问到错误的状态。
> - **违反封装原则**：构造器中调用可以被覆盖的方法可能会导致子类的实现细节泄露到父类中。
> 
> 尽管可以在父类构造器中调用被子类实现的方法，但这种做法通常是不推荐的。因为这违背了 Java 编程中的安全构造器实践。正确的做法是，构造器应该避免调用可以被覆盖的方法（也就是非 `final` 的方法），特别是在抽象类的构造器中，这样做可以避免在子类构造器执行之前，访问未初始化的状态。 

# Base de Java

> [!question] Les différences entre `String`, `StringBuffer`, `StringBuilder` #string #stringbuffer #stringbuilder 
> - `String` est immuable
> - `StringBuffer` est thread safe
> - `StringBuilder` est pas thread safe
> - Réunir les strings par `StringBuilder` sera plus efficacement 

> [!question] C'est quoi une énumération ? #enum 
> C'est une variable spécifique, elle contient un ou plusieurs valeurs constantes

> [!question] 
> une enumeration Java peut elle apporter de traitement métier si oui comment. 

## Exception

> [!question] Qu’est-ce que ça évoque pour vous « exception » et unchecked ou checked ? #exception 
> En gros, l'exception une erreur de programme, il y a trois type, error, runtime exception et checked exception
> - Error représente une erreur grave, qui se produit dans JVM ou un sous système Java. 
> - Runtime exception a lieu lors d'exécution, doit être prévu et traité par le développeur. 
> - Checked exception est détecté par le compilateur pendant le développement, il faut le corriger avant le compilation.
> 
> Error et Runtime exception sont unchecked exception

> [!question] Comment tu crées une nouvelle exception ? #exception 
> Créer une sous-classe d'exception/runtime exception, puis réécrire les méthodes nécenssaires

> [!question] 2 exemples de type unchecked exception & 2 exemples de check exception #exception 
> Error: `OutOfMemoryError`, `VituralMachineError`
> Runtime exception: `ClassCastException`, `NullPointerException`, `IndexOutOfBoundsException`
> Checked exception `ClassNotFoundException`, `FileNotFoundException`

## Les collections 

- Les structures de données (`List`, `Set`, `Map`…). 
- `Map` et `List` en priorité, implantation `ArrayList`, `LinkedList` avantage/ inconvénient, complexité algorithmique en recherche. 
- `Map`, `HashMap`, `ConcurrentHashMap` 

> [!question] 
> 如何选用集合?
> / 说说 List, Set, Queue, Map 四者的区别？ #collection
> -   `List`(对付顺序的好帮手): 存储的元素是有序的、可重复的。
> -   `Set`(注重独一无二的性质): 存储的元素是无序的、不可重复的。
> -   `Queue`(实现排队功能的叫号机): 按**特定的排队规则**来确定先后顺序，存储的元素是有序的、可重复的。
> -   `Map`(用 key 来搜索的专家): 使用键值对（key-value）存储

> [!question] Plus facile de retrouver un élément sur une list ou sur un set ? #list #set 
> Set

### List

> [!question] 
> Quelle sont les classes d'implémentation principaux dans `List` et ses caractères principaux 
> / Différence `ArrayList` et `LinkedList` ? #list #arraylist #linkedlist 
> 
`ArrayList`, il est réalisé par un array d'objet, plus efficace pour la recherche
>  `LinkedList`, réalisé par la liste doublement chainée, plus efficace pour l'insertion et la suppression
>  `Vector`, thread-safe
>  Ils sont ordonnés, accepte les éléments doublons et null

### Set

> [!question] 
> Quelle sont les classes d'implémentation principaux dans `Set` et ses caractères principaux 
> / Les différences entre `HashSet`, `LinkedHashSet`et `TreeSet`
> / `HashSet` vous voyez a quoi ça sert ? #set #hashset #linkedhashset #treeset 
> 
> `HashSet`, réalisé par `HashMap`, accepte null
> `LinkedHashSet`, réalisé par `LinkedHashMap`, il est ordonné en FIFO
> `TreeSet`, réalisé par black red tree, il est aussi ordonné, en tri naturel par défaut, ou en tri personnalisé, thread-safe
> Ils acceptent pas la valeur doublons

> [!question] 
> Comment `HashSet` gère les doublons/Comment `HashSet` fait pour pas qu'il y a de doublon.
> / Quand on veut rajouter un élément dans une `HashSet` que fait le code java? #hashset 
> 
> Il compare tout d'abord les hash-codes de deux éléments
> - S'ils sont différents, la nouvelle élément va être enregistrée selon son hash-codes
> - S'ils sont pareil, il compare ensuite les objets par la fonction equals, si c'est différente, on garde aussi la nouvelle élément, sinon, on va le perdre.

| Set           | add     | contains | insert/remove |
| ------------- | ------- | -------- | ------------- |
| HashSet       | O(1)    | O(1)     | O(1)          |
| LinkedHashSet | O(1)    | O(1)     | O(1)          |
| TreeSet       | O(logn) | O(logn)  | O(logn)       |

### Map

> [!question] 
>  Quelle sont les classes d'implémentation principaux dans `Map` et ses caractères principaux 
>  / Une implémentation de `Map` thread-safe ? #map 
>  / La différence entre `HashMap` et `HashTable` #hashmap #hashtable 
>  
>  - `HashMap`, accepte null, utilise iterator
>  - `TreeMap`, ordonné avec tri naturel ou tri personnel
>  - `HashTable`, thread-safe,  utilise Enumeration

> [!question] Est ce c'es possible de transformer `HashMap` en synchrone #hashmap 
> 1. Par la méthode `Collections.synchronizedMap()`
> 2. Utiliser directement `ConcurrentHashMap`

> [!question] Pourquoi l'agrandissement de `HashMap` est deux fois la capacité de l'original. #hashmap 
> Chaque élément est ajouté dans `HashMap`, le position d’élément est déterminé par `hashcode` et l’opération ET bit-à-bit avec la capacité en binaire. Si la capacité est toujours multipliée par 2, on ne compare que les 4 5 6 derniers chiffres.

> [!question] Quel est l'évolution de l'agrandissement de `HashMap` depuis 1.8 #hashmap 

| Map               | add     | contains |
| ----------------- | ------- | -------- |
| HashMap           | O(1)    | O(1)     |
| TreeMap           | O(logn) | O(logn)  |
| ConcurrentHashMap | O(1)    | O(1)     |

# Avancé

## Stream

> [!question] C’est quoi les différentes opérations qu’on peut faire sur les streams ? #stream 

> [!question] C’est quoi map et flapmap ? #stream 

## Thread

> [!question] Connaissance du multithreading #thread , (deadlock #deadlock, création de thread, synchronisation des thread)

> [!question] `Thread`, `Runnable`, 和`Callable`的区别：

> [!question] mot clés synchronized ou mutex ou semaphore> 

> [!question] thread pool (à quoi ça sert…)

> [!question] mot clé volatile… #volatile 

> [!question] Concurentmodificationexception 解决办法 
> 
> ![[Pasted image 20231127220539.png]]

## JVM
#jvm 

Gestion de la mémoire (les différents espaces mémoire …) le fonctionnement du GC..

La mémoire est géré automatiquement par JVM, l'allocation, l'utilisation et la libération par garbage collector. Il a plusieurs zone de mémoire, stack, heap, et method area


