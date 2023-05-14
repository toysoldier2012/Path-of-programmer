
> [!question] 
> **Q: Les caractères de Java POO** #D1 
> - [[Programmation orientée objet#^c61b13|Encapsulation]] est pour cacher les datas et les méthodes sensitives
> - [[Programmation orientée objet#^d8a3bb|Héritage]] évide la duplication de code et augmente la réutilisabilité
> - [[Programmation orientée objet#^32c4f7|Polymorphisme]] est override

# Les Caractères principaux 

## 1. Encapsulation
#encapsulation 

### 1.1 Règles de visibilité
^683229

![[Pasted image 20230419214403.png]]

### 1.2 [[Module]]

![[Pasted image 20221211225959.png]]

一个模块是一个jar文件， 但是比普通jar文件多一个module-info.class文件，即module descriptor

### 1.3 Package
#package 

import

-   java.lang: Contains fundamental classes and interfaces such as Object, String, and Math.
-   java.util: Contains utility classes and interfaces such as List, Set, and Map.
-   java.io: Provides input and output functionality through classes such as File, InputStream, and OutputStream.
-   java.net: Provides networking functionality through classes such as URL, InetAddress, and Socket.
-   java.time: Provides classes for working with dates, times, and intervals, such as LocalDate, LocalTime, and Duration.
-   java.awt: Provides classes for building graphical user interfaces (GUIs).
-   javax.crypto: Provides classes and interfaces for cryptographic operations.
-   javax.xml: Provides classes and interfaces for working with XML.

## 2. Héritage
#heritage

## 3. Polymorphism
#polymorphism 

- Complie-time polymorphism

重载overload

- Runtime polymorphism or Dynamic Method Dispatch

重写 override
#override 

需要注意多态的类型 大转小需要强转，因此在类型转换时需要先通过instanceof做判断


# [[Classe]]

# Objet

- 匿名对象

