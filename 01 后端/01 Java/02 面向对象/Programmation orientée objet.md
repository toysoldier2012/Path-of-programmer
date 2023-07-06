#oop

# Les Caractères principaux 

## 1. Encapsulation
#encapsulation 

### 1.1 Les modificateurs d'accès
#visibility

### 1.2 [[Module]]

![[Pasted image 20221211225959.png]]

### 1.3 Package
#package 

#### Les packages standards:

- `java.lang`: Classes et interfaces fondamentales comme `Object`, `String`, et `Math`.
- `java.util`: Les utilitaires comme les collections `List`, `Set`, et `Map`, internationalisation, logging, expression régulières.
- `java.io`: Accès aux flux entrants et sortants comme `File`, `InputStream`, et `OutputStream`.
- `java.time`: Provides classes for working with dates, times, and intervals, such as `LocalDate`, `LocalTime`, and `Duration`.
- `java.math`: 
- `java.sql`: Accès aux bases de données

- `java.net`: Accès aux réseaux comme `URL`, `InetAddress`, and `Socket`.
- `javax.xml`: Provides classes and interfaces for working with XML.
- `java.applet`: Création d'applets
- `java.security`: Mise en oeuvre de fonctionnalités concernant la sécurité

- `java.awt`: Création d'interfaces graphiques avec AWT.
- `java.nio`: API NIO
- `java.rmi`: Invocation de méthodes distantes
- `javax.crypto`: Provides classes and interfaces for cryptographic operations.

> [!todo] 
> 1. Les principaux packages d'extensions
> 2. Les principaux packages tiers

#### Import package


## 2. Héritage
#heritage

需要注意多态的类型大转小需要强转，因此在类型转换时需要先通过 `instanceof` 做判断 #instanceof

## 3. Polymorphisme
#polymorphism 

Le polymorphisme est la capacité, pour un même message de correspondre à plusieurs formes de traitement selon l'objet auquel ce message est adressé

On peut affecter à une référence d'une classe n'import quel objet d'une de ses sous-classe




- Complie-time polymorphism/Overload/Surchargé #overload
- Runtime polymorphism or Dynamic Method Dispatch/Override/Redéfinition #override 

Le polymorphisme est un concept clé de la programmation orientée objet (POO) qui permet à un objet de prendre différentes formes ou comportements. Il permet à un objet d'être traité comme une instance de sa propre classe ou comme une instance d'une de ses classes dérivées.

Le polymorphisme se manifeste de deux manières principales :

1. **Polymorphisme de sous-type (subtype polymorphism)** : Cela se produit lorsque différentes classes sont liées par une relation d'héritage (classe de base et classes dérivées) et qu'un objet d'une classe dérivée peut être traité comme un objet de la classe de base. Cela signifie que vous pouvez utiliser un objet de la classe dérivée partout où un objet de la classe de base est attendu. Le polymorphisme de sous-type permet d'utiliser le principe de substitution, où les méthodes de la classe de base peuvent être redéfinies dans les classes dérivées avec un comportement spécifique à la classe dérivée.
    
2. **Polymorphisme paramétrique (parametric polymorphism)** : Cela se produit lorsque des méthodes ou des classes sont génériques et peuvent être utilisées avec différents types de données sans avoir à spécifier le type de données spécifique à l'avance. Cela permet de créer des méthodes ou des classes réutilisables et flexibles qui peuvent être utilisées avec différents types de données.
    

Le polymorphisme offre plusieurs avantages, notamment :

- Flexibilité et extensibilité : Il permet d'écrire du code générique qui peut être utilisé avec différents types de données et facilite l'ajout de nouvelles classes dérivées sans modifier le code existant.
- Réutilisation du code : Le polymorphisme permet de définir des comportements communs dans une classe de base, qui peuvent être hérités et utilisés par les classes dérivées.
- Encapsulation : Le polymorphisme permet d'utiliser une interface commune (la classe de base) pour manipuler des objets de différentes classes dérivées, ce qui cache les détails spécifiques de chaque classe.

En résumé, le polymorphisme est un concept puissant de la POO qui permet de traiter les objets de différentes classes de manière uniforme, d'améliorer la réutilisation du code et d'augmenter la flexibilité et l'extensibilité des applications.

# [[Classe]]

# Objet

- 匿名对象

