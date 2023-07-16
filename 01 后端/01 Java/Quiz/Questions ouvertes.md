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
> Quelle sont les classes d'implémentation principaux dans `List` et ses caractères principaux #list 
> / Différence `ArrayList` et `LinkedList` ? #arraylist #linkedlist 
> 
`ArrayList`, il est réalisé par un array d'objet, plus efficace pour la recherche
>  `LinkedList`, réalisé par la liste doublement chainée, plus efficace pour l'insertion et la suppression
>  `Vector`, thread-safe
>  Ils sont ordonnés, accepte les éléments doublons et null

| List       | get  | add  | contains | insert/remove |
| ---------- | ---- | ---- | -------- | ------------- |
| ArrayList  | O(1) | O(1) | O(n)     | O(n)          |
| LinkedList | O(n) | O(1) | O(n)     | O(1)          |

### Set

> [!question] 
> Quelle sont les classes d'implémentation principaux dans `Set` et ses caractères principaux #set 
> / Les différences entre `HashSet`, `LinkedHashSet`et `TreeSet` #hashset #linkedhashset #treeset 
> / `HashSet` vous voyez a quoi ça sert ? #hashset 
> 
> `HashSet`, réalisé par `HashMap`, accepte null
> `LinkedHashSet`, réalisé par `LinkedHashMap`, il est ordonné en FIFO
> `TreeSet`, réalisé par black red tree, il est aussi ordonné, en tri naturel par défaut, ou en tri personnalisé, thread-safe
> Ils acceptent pas la valeur doublons

> [!question] 
> Comment `HashSet` gère les doublons/Comment `HashSet` fait pour pas qu'il y a de doublon.
> / Quand on veut rajouter un élément dans une `HashSet` que fait le code java? #hashset 

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

#todo relire

> [!question] C’est quoi map et flapmap ? #stream 

## Thread
#todo 

> [!question] 
> Connaissance du multithreading #thread , (deadlock #deadlock, création de thread, synchronisation des thread)
> mot clés synchronized ou mutex ou semaphore
> thread pool (à quoi ça sert…)
> mot clé volatile… 

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