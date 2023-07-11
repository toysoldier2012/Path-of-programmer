# Les fondamentaux du langue objet 

## Q: Pk langage objet plutôt que langage procédurale ? #oop 

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

## Couplage entre les objets? #oop #coupler

- Un couplage fort signifie que les classes et les objets dépendent les uns des autres. 
- En général, le couplage fort n’est pas bon car il réduit la flexibilité et la réutilisation du code

Différence héritage et composition ?

C'est quoi une énumération ?

Peut-on Faire un overide sur une methode static ?






#### Q : Les différences entre `String`, `StringBuffer`, `StringBuilder` #string #stringbuffer #stringbuilder 

- `String` 是不可变的
- `StringBuffer` 对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全的。
- `StringBuilder` 更快，线程不安全
- 拼接字符最好不要用 `String + String` 或者  `"chaine1"&&"chaine2"`，过程中会创建 n 个 `StringBuilder`



Injection de dépendance?







+Les structures de données (list, set, map…). Map et list en priorité, implantation arrawlist, linkedlist avantage/ inconvénient, complexité algorithmique en recherche. Map, Hmap, concurrent hmpap …

+Connaissance du **multithreading**, (deadloack, création de thread, synchronisation des thread (mot cles synchronized ou mutex ou semaphore) , thread pool (à quoi ça sert…), mot clé volatile…

+Java 8 (stream, lambda…)

+ Gestion de la mémoire (les différents espaces mémoire …) le fonctionnement du GC..

Exemple de questions :




Hmap ? Comment ça fonctionne ?

Une implémentation de Map treadsafe ?



Pour implémenter une arrawlist de quoi tu as besoin?

Hset et treeset

Différence arawlist et linkedlist ?

Complexité Algo en recherche ?

Quand on veut rajouter un élément dans une Hset que fait le code java?

Hcode…

Hset comment elle gère les doublons?

Comment elle fait pour pas qu'il y ai de doublon.

2 exemples de type unchecked exception

2 exemples de check exception




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