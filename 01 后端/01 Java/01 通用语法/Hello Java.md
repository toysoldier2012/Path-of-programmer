
# La compilation et l'exécution
#compiler

![[Pasted image 20230622161652.png]]

> [!todo] 
>  1. La processus de la compilation
>  2. La compilation de la classe anonyme
>  3. Le déploiement sous la forme d'un jar
>  4. classpath

# JDK, JRE, JVM
#jdk #jre #jvm

# Les identifiants
#identifier

Les identifiants sont utilisés pour nommer des éléments du code source de Java, notamment les variables, les classes, les méthodes, les paramètres, les packages, les interfaces, les modules, les énumérations, les étiquettes. 

**Ils sont sensibles à la casse.**

## Des normes de nommage

- `NameOfClass` : est le nom d'une classe
- `nameOfMain` : est le nom d'une méthode
- `nameOfValeur` : est le nom d'une variable locale

## Les mots réservés
#keyword 

- 51 mots clés (keywords) dont 2 ne sont pas utilisés(`const` et `goto`)
- 3 valeurs littérales (literals) : true, false et null

|  |              |            |          |           |           |
| ---------- | ------------ | ---------- | -------- | --------- | --------- |
| abstract   | assert       | boolean    | break    | byte      | case      |
| catch      | char         | class      | const(x) | continue  | default   |
| double     | do           | else       | enum     | extends   | false     |
| final      | finally      | float      | for      | goto(x)   | if        |
| implements | import       | instanceof | int      | interface | long      |
| native     | new          | null       | package  | private   | protected |
| public     | return       | short      | static   | strictfp  | super     |
| switch     | synchronized | this       | throw    | throws    | transient |
| true       | try          | void       | volatile | while     |           |

| Java 9(les mots réservés dans ficher module) | Java 10 | Java 13 | Java 16 |
| -------------------------------------------- | ------- | ------- | ------- |
| exports                                      | var     | yield   | record  |
| module                                       |         |         |         |
| open                                         |         |         |         |
| opens                                        |         |         |         |
| provides                                     |         |         |         |
| requires                                     |         |         |         |
| to                                           |         |         |         |
| transitive                                   |         |         |         |
| uses                                         |         |         |         |
| with                                         |         |         |         |

# Les commentaires
#comment 

- Le commentaire abrégé
- Le commentaire multiligne
- Le commentaire de documentation automatique

# [[Variable]]

# Opérateur
#operator 

- Les opérateurs arithmétiques

``` java
expr++ //incrément
expr-- //Decrement
++expr --expr +expr -expr !expr
+ - *  /  %

=  +=  -=  *=  /=  %=  ^=  |=  <<=  >>=  >>>= ->
```

- Les opérateurs de bits

```java
//位运算符 opérateur de bits
^ //异或 opérateur ou exclusif
& //opérateur et
| //opérateur ou
<< //opérateur décalage à gauche
>> //opérateur décalage à droit
>>> //opérateur décalage à droit non signe
~ //opérateur non
```

- Les comparaisons

```java
<  >  <=  >=  instanceof == !=
&& ||
? :
```

> [!attention] 
> Lors d'une opération sur les opérandes de type différents, le compilateur détermine le type du résultat en prenant le type le plus précis des opérandes.
> Ex: int b = 5; short c = 1; int a = b + c;
> 

# Les structures de contrôles

## Les branchements conditionnels
#branche

- if
- switch
	- la chaine de caractère ne soit pas null
	- **Si une instruction case ne contient pas de break, alors les traitements associées au case suivant sont exécutés. Cela permet d'exécuter les mêmes instructions pour plusieurs valeurs.**
- l'opération ternaire

## Les boucles

^6c83db

#circle

- for
- while
- for-each (for évoluée)

Les débranchement

- break
- continue

# Syntactic sugar

#todo 

# 进制

#todo 