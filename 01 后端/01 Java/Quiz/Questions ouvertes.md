# Les fondamentaux du langue objet 

## Q: Pourquoi langage objet plutôt que langage procédurale ? #oop 

- Certains caractères permet de faciliter le développement.
- C'est une modélisation du monde réel, qui permet d'une représentation de concept complexe de manière plus naturelle

## Q: Les caractères de POO #oop 
 
- Encapsulation est pour cacher les datas et les méthodes sensitives
- Héritage évide la duplication de code et augmente la réutilisabilité
- Polymorphisme est override

## Q: Quelles sont les différences entre class abstraite et interface #interface #abstract

1.  Les classes abstracts ne peuvent avoir que simple héritage, et les interface peuvent avoir multi héritage
2.  Les classes abstracts peuvent avoir les constructeurs
3.  Les classes abstracts peuvent avoir les attributs
4.  Dans les interfaces, tous les méthodes sont abstracts, après Java 8, les méthodes défaut et les méthodes statiques sont acceptés
5.  Dans les interfaces, avant Java 9, la visibilité de méthode est que public, maintenant il peut être aussi privates et private statique
====6.  L'interface est une abstraction d'un comportement spécifique.====
====7.  La classe abstract est une abstraction d'un type de chose.====

## Différence héritage et composition ? #heritage #composition

1. L'héritage est un relation is-a
2. La composition est un relation has-a

## Peut-on Faire un override sur une méthode static ?

Non, les méthodes static avec le même nom existent dans le même temps lors de héritage


## Couplage entre les objets? #oop #coupler

- Un couplage fort signifie que les classes et les objets dépendent les uns des autres. 
- En général, le couplage fort n’est pas bon car il réduit la flexibilité et la réutilisation du code

# Les APIs de base

#### Q : Les différences entre `String`, `StringBuffer`, `StringBuilder` #string #stringbuffer #stringbuilder 

- `String` 是不可变的
- `StringBuffer` 对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全的。
- `StringBuilder` 更快，线程不安全
- 拼接字符最好不要用 `String + String` 或者  `"chaine1"&&"chaine2"`，过程中会创建 n 个 `StringBuilder`

# C'est quoi une énumération ? #enum 

## Java 8 (stream, lambda…)

## Les collections 

Les structures de données (`List`, `Set`, `Map`…). `Map` et `List` en priorité, implantation `ArrayList`, `LinkedList` avantage/ inconvénient, complexité algorithmique en recherche. `Map`, `HashMap`, `ConcurrentHashMap` 

`HashMap` ? Comment ça fonctionne ?

Une implémentation de `Map` thread-safe ?

Pour implémenter une `ArrayList` de quoi tu as besoin?

`HashSet` et `TreeSet`

Différence `ArrayList` et `LinkedList` ?

Complexité Algo en recherche ?

Quand on veut rajouter un élément dans une `HashSet` que fait le code java?

hashcode…

`HashSet` comment elle gère les doublons?

Comment elle fait pour pas qu'il y a de doublon.

> [!question]
> Q: 比较 HashSet、LinkedHashSet 和 TreeSet 三者的异同 #D1 
> -   `HashSet`、`LinkedHashSet` 和 `TreeSet` 都是 `Set` 接口的实现类，都能保证元素唯一，并且都不是线程安全的。
> -  `HashSet`、`LinkedHashSet` 和 `TreeSet` 的主要区别在于底层数据结构不同。`HashSet` 的底层数据结构是哈希表（基于 `HashMap` 实现）。`LinkedHashSet` 的底层数据结构是链表和哈希表，元素的插入和取出顺序满足 FIFO。`TreeSet` 底层数据结构是红黑树，元素是有序的，排序的方式有自然排序和定制排序。
> - 底层数据结构不同又导致这三者的应用场景不同。`HashSet` 用于不需要保证元素插入和取出顺序的场景，`LinkedHashSet` 用于保证元素的插入和取出顺序满足 FIFO 的场景，`TreeSet` 用于支持对元素自定义排序规则的场景

> [!question] 
> **Q: La différence entre HashMap et HashTable** #D1 
> 
> 1. Complètement différent, HashMap est subClass de AbstractMap et HashTable est subClass de Dictionary
> 2. La taille initiale est différent, HashMap est 16, HashTable est 11
> 3. HashTable est synchronisé
> 4. HashMap peut sauvegarder nul
> 5. HashMap utilise iterator, HashTable utilise Enumeration 
> 
> Q: 说说 List, Set, Queue, Map 四者的区别？ #D1 
> 
> -   `List`(对付顺序的好帮手): 存储的元素是有序的、可重复的。
> -   `Set`(注重独一无二的性质): 存储的元素是无序的、不可重复的。
> -   `Queue`(实现排队功能的叫号机): 按**特定的排队规则**来确定先后顺序，存储的元素是有序的、可重复的。
> -   `Map`(用 key 来搜索的专家): 使用键值对（key-value）存储，类似于数学上的函数 y=f(x)，"x" 代表 key，"y" 代表 value，key 是无序的、不可重复的，value 是无序的、可重复的，每个键最多映射到一个值。
> 
> Q: 如何选用集合? #D1 
> 
> - 需要根据键值获取到元素值时就选用 `Map` 接口下的集合，需要排序时选择 `TreeMap`,不需要排序时就选择 `HashMap`,需要保证线程安全就选用 `ConcurrentHashMap`。
> - 当我们只需要存放元素值时，就选择实现`Collection` 接口的集合，需要保证元素唯一时选择实现 `Set` 接口的集合比如 `TreeSet` 或 `HashSet`，不需要就选择实现 `List` 接口的比如 `ArrayList` 或 `LinkedList`，然后再根据实现这些接口的集合的特点来选用。



## 2 exemples de type unchecked exception & 2 exemples de check exception #exception 


Injection de dépendance?

+
+Connaissance du **multithreading**, (deadloack, création de thread, synchronisation des thread (mot cles synchronized ou mutex ou semaphore) , thread pool (à quoi ça sert…), mot clé volatile…

+ Gestion de la mémoire (les différents espaces mémoire …) le fonctionnement du GC..




**Exemple de live coding :**

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