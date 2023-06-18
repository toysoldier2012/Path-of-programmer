#oop

# Les Caractères principaux 

## 1. Encapsulation
#encapsulation 

### 1.1 Règles de visibilité
#visibility

|Modifier|Visibility|
|---|---|
|`private`|None|
|No modifier (default)|Classes in the package|
|`protected`|Classes in package and subclasses inside or outside the package|
|`public`|All classes|

### 1.2 [[Module]]

![[Pasted image 20221211225959.png]]

### 1.3 Package
#package 

import

- `java.lang`: Contains fundamental classes and interfaces such as Object, String, and Math.
- `java.util`: Contains utility classes and interfaces such as List, Set, and Map.
- `java.io`: Provides input and output functionality through classes such as File, `InputStream`, and `OutputStream`.
- `java.net`: Provides networking functionality through classes such as URL, `InetAddress`, and Socket.
- `java.time`: Provides classes for working with dates, times, and intervals, such as `LocalDate`, `LocalTime`, and `Duration`.
- `java.awt`: Provides classes for building graphical user interfaces (GUIs).
- `javax.crypto`: Provides classes and interfaces for cryptographic operations.
- `javax.xml`: Provides classes and interfaces for working with XML.

## 2. Héritage et Polymorphism
#heritage
#polymorphism 

- Complie-time polymorphism/Overload/Surchargé #overload
- Runtime polymorphism or Dynamic Method Dispatch/Override/Redéfinition #override 

需要注意多态的类型 大转小需要强转，因此在类型转换时需要先通过instanceof做判断

# [[Classe]]

# Objet

- 匿名对象

