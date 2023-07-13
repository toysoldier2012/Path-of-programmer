# Les fondamentaux du langue objet 

> [!question] Pourquoi langage objet plutôt que langage procédurale ? #oop 
> - Certains caractères permet de faciliter le développement.
> - C'est une modélisation du monde réel, qui permet d'une représentation de concept complexe de manière plus naturelle 

> [!question] Les caractères de POO #oop 
> - Encapsulation est pour cacher les datas et les contenus sensitifs
> - Héritage et Polymorphisme augmente la réutilisabilité
> - On a deux type de polymorphisme, override et overload

> [!question] Couplage entre les objets? #oop #coupler 
> - Un couplage fort signifie que les classes et les objets dépendent les uns des autres. 
> - En général, le couplage fort n’est pas bon car il réduit la flexibilité et la réutilisation du code 

> [!question] Quelles sont les différences entre class abstraite et interface #interface #abstract 
> - Les classes abstracts ne peuvent avoir que simple héritage, et les interface peuvent avoir multi héritage
> - Les classes abstracts peuvent avoir les constructeurs
> - Les classes abstracts peuvent avoir les attributs
> - Dans les interfaces, tous les méthodes sont abstracts, après Java 8, les méthodes défaut et les méthodes statiques sont acceptés
> - Dans les interfaces, avant Java 9, la visibilité de méthode est que public, maintenant il peut être aussi privates et private statique
> - ==L'interface est une abstraction d'un comportement spécifique.==
> - ==La classe abstract est une abstraction d'un type de chose.== 

> [!question] Différence héritage et composition ? #heritage #composition 
> - L'héritage est un relation is-a
> - La composition est un relation has-a 

> [!question] Peut-on Faire un override sur une méthode static ? #override #static 
Non, on peut pas réaliser le polymorphisme sur la méthode statique, cette dernière appartient une classe mais pas un objet 

# Base de Java

#todo hashcode

> [!question] Les différences entre `String`, `StringBuffer`, `StringBuilder` #string #stringbuffer #stringbuilder 
> - `String` est immuable
> - `StringBuffer` est thread safe
> - `StringBuilder` est pas thread safe
> - Réunir les strings par `StringBuilder` sera plus efficacement 

> [!question] C'est quoi une énumération ? #enum 

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

> [!question] 如何选用集合? #collection 
> - 需要根据键值获取到元素值时就选用 `Map` 接口下的集合，需要排序时选择 `TreeMap`,不需要排序时就选择 `HashMap`,需要保证线程安全就选用 `ConcurrentHashMap`。
> - 当我们只需要存放元素值时，就选择实现`Collection` 接口的集合，需要保证元素唯一时选择实现 `Set` 接口的集合比如 `TreeSet` 或 `HashSet`，不需要就选择实现 `List` 接口的比如 `ArrayList` 或 `LinkedList`，然后再根据实现这些接口的集合的特点来选用。

> [!question] 说说 List, Set, Queue, Map 四者的区别？ #collection
> -   `List`(对付顺序的好帮手): 存储的元素是有序的、可重复的。
> -   `Set`(注重独一无二的性质): 存储的元素是无序的、不可重复的。
> -   `Queue`(实现排队功能的叫号机): 按**特定的排队规则**来确定先后顺序，存储的元素是有序的、可重复的。
> -   `Map`(用 key 来搜索的专家): 使用键值对（key-value）存储，类似于数学上的函数 y=f(x)，"x" 代表 key，"y" 代表 value，key 是无序的、不可重复的，value 是无序的、可重复的，每个键最多映射到一个值。

> [!question] Plus facile de retrouver un élément sur une list ou sur un set ? #list #set 

> [!question] Complexité Algo en recherche ? #collection

### List

> [!question] 
> Quelle sont les classes d'implémentation principaux dans `List` et ses caractères principaux #list 
> / Différence `ArrayList` et `LinkedList` ? #arraylist #linkedlist 
> 
`ArrayList`, il est réalisé par un array d'objet, plus efficace pour la recherche
>  `LinkedList`, réalisé par la liste doublement chainée, plus efficace pour l'insertion et la suppression
>  `Vector`, thread-safe
>  Ils sont ordonnés, accepte les éléments doublons et null

### Set

> [!question] 
> Quelle sont les classes d'implémentation principaux dans `Set` et ses caractères principaux #set 
> / Les différences entre `HashSet`, `LinkedHashSet`et `TreeSet` #hashset #linkedhashset #treeset 
> / `HashSet` vous voyez a quoi ça sert ? #hashset 
> 
> `HashSet`, réalisé par xxxx, accepte null,
> `LinkedHashSet`, réalisé par xxxx, il est ordonné en FIFO
> `TreeSet`, réalisé par black red tree, il est aussi ordonné, il est en tri naturel par défaut, ou on définit le tri personnalisé, accepte que les éléments dans la même classe
> Ils acceptent pas la valeur doublons

#todo 各个set的底层实现

> [!question] 
> Comment `HashSet` gère les doublons/Comment `HashSet` fait pour pas qu'il y a de doublon.
> / Quand on veut rajouter un élément dans une `HashSet` que fait le code java? #hashset 

### Map

> [!question] Une implémentation de `Map` thread-safe ? #map 

> [!question] `HashMap` ? Comment ça fonctionne ? #hashmap 

> [!question] La différence entre `HashMap` et `HashTable` #hashmap #hashtable 
> - La taille initiale est différent, `HashMap` est 16, `HashTable` est 11
> - `HashTable` est synchronisé
> - `HashMap` peut sauvegarder nul
> - `HashMap` utilise iterator, `HashTable` utilise Enumeration 

> [!question] Est ce c'es possible de transformer `HashMap` en synchrone #hashmap 
> 1. Par la méthode `Collections.synchronizedMap()`
> 2. Utiliser directement `ConcurrentHashMap`

> [!question] Quel est l'évolution de l'agrandissement de `HashMap` depuis 1.8 #hashmap 

> [!question] Pourquoi l'agrandissement de `HashMap` est deux fois la capacité de l'original. #hashmap 
> Chaque élément est ajouté dans `HashMap`, le position d’élément est déterminé par `hashcode` et l’opération ET bit-à-bit avec la capacité en binaire. Si la capacité est toujours multipliée par 2, on ne compare que les 4 5 6 derniers chiffres.

> [!question] A quoi doit-on faire attention quand on utilise une clé en `HashMap` ? #hashmap 

# Avancé

## Stream
#todo

> [!question] C’est quoi les différentes opérations qu’on peut faire sur les streams ? #stream 

> [!question] C’est quoi map et flapmap ? #stream 

## Thread
#todo 

Connaissance du **multithreading**, (deadlock, création de thread, synchronisation des thread (mot clés synchronized ou mutex ou semaphore) , thread pool (à quoi ça sert…), mot clé volatile…

## JVM
#todo 

Gestion de la mémoire (les différents espaces mémoire …) le fonctionnement du GC..





Injection de dépendance?

live coding

Input : Collection de String
output : La String la plus longue commune à tous les inputs

AAA, AAB, AAC -> AA
ABC, ABD, ACF -> A
ABC, BCD -> BC
AZE, QSD -> ""

**Autre exo**

Sortir les occurrences redondantes :

A,B,C,A -> A
A,X,A,X,B -> A,X
C,B,C,C,C,B,N -> C,B