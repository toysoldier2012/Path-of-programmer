#class 

# Sections

1. Déclaration de donnée
2. Constructeur
3. Déclaration de [[Méthode]] 
4. Block

# Les Mots clés
#keyword

- [[Programmation orientée objet#1.1 Les modificateurs d'accès|Les modificateurs d'accès]] 

- #static 

Elle ne sont définies qu'une seule fois, quel que soit le nombre d'objet instanciés de la class Non-static entity ne peut pas être utilisé dans static méthode

- #final

S'appliquer aux variable, les méthodes ou les classes
- Le référence de variable ne peut plus être changé, mais pour les collections, les contenus est toujours modifiable, si on veut un collection unmodifiable, voir [[Collections#^a35227||Collections]]
- Méthode ne peut plus réécrit
- La sous classe est interdit pour une classe finale

- #instanceof 

Pour déterminer la classe d'un objet, voir aussi [[Variable#^3367ba||cast]] 

- #this 

This est un instance d'un objet dans lequel il est utilisé
	
- #super

- #synchronized 

- #volatile 

- #native

Une méthode native est une méthode implémenté en C++, il a la limite de la portabilité, mais avec une vitesse d'exécution plus rapide 

# Comparaison

## `==` et `equals()` 
#equals 

## `hashCode()`
#hashcode

如果重写 `equals()` 时没有重写 `hashCode()` 方法的话，就可能会导致相等的两个对象，`hashCode` 值却不相等。

# Classe spécifique

## 1. Classe abstract 
#abstract 

## 2. Interface 
#interface 

- L'interface est une abstraction d'un comportement spécifique.
- Les seules variables que l'on peut définir dans une interface sont des variables de la classe qui doivent être constantes 
- Toute classe qui implémente cette interface, doit au moins posséder les méthodes qui sont déclarées dans l'interface

- Java 9 之后，方法可以为 `private` 或者 `private static`

### La `default` méthode
#default

- Après Java 8, la méthode `default` permet de définir le comportement dans l'interface auquel elle est définie, elle évide de la redéfinir dans tous les classes d'implémentation 

- Il est possible de créer directement une instance d'une interface si tous les méthodes sont méthodes par défaut
- Une interface fille peut redéfinir la méthode par défaut sans le déclarer par défaut, dans ce cas elle redéfinir comme étant abstraite

- Dans la classe d'implémentation, on rappelle la méthode défaut dans l'interface par `Interface.super.method()

### L'interface locale

Elle ne capture que les variables statics du context englobant

### L'interface fonctionnelle

Elle a qu'une seule méthode abstraite

## 内部类 `

[Java内部类详解_weixin_30578677的博客-CSDN博客](https://blog.csdn.net/weixin_30578677/article/details/99659725?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1-99659725-blog-78625320.235%5Ev38%5Epc_relevant_sort&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-1-99659725-blog-78625320.235%5Ev38%5Epc_relevant_sort&utm_relevant_index=2)

- 匿名内部类 #anonymousclass 

