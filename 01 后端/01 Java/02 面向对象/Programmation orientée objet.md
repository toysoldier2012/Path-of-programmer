#oop

# Les Caractères principaux 

## 1. Encapsulation
#encapsulation 

### 1.1 Les modificateurs d'accès
#visibility

| Modifier           | Visibility                                       |
| ------------------ | ------------------------------------------------ |
| `private`          | None                                             |
| Sans modificateurs | Classes dans la même package                     |
| `protected`        | Classes dans la même package et les sous-classes |
| `public`           | Partout                                          | 

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
#heritage #super 

Il est obligatoire dans un constructeur d'une classe fille de faire appel explicitement ou implicitement au constructeur de la classe mère.
## 3. Polymorphisme
#polymorphism 

Le polymorphisme permet de traiter les objets de différentes classes de manière uniforme, d'améliorer la réutilisation du code et d'augmenter la flexibilité et l'extensibilité des applications.

# [[Classe]]

# Objet

- 匿名对象

