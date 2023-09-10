#operator 

- Lors d'une opération sur les opérandes des types différents, le compilateur détermine le type du résultat en prenant le type le plus précis des opérandes.

# Types

## Les opérateurs arithmétiques

``` java
expr++ ++expr //incrément
expr-- --expr //Decrement
+expr -expr !expr
+ - *  /  %

// Ex.
int/0 //rapporte ArithmeticException
Math.sqrt(-1) // = Double.NaN
0.0/0 //  = Double.NaN

=  +=  -=  *=  /=  %=  ^=  |=  <<=  >>=  >>>= 
// Si le type de résultat d'un expression est différent que l'opérant, la cast se produit

->
```

## Les opérateurs de bits

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

## Les comparaisons

```java
<  >  <=  >=  instanceof == !=
&& || !
? :
```

## Switch

- Le type de case doit être `int`, `String`, `Enum`
- Le case ne soit pas null
- Si une instruction case ne contient pas de break, alors les traitements associées au case suivant sont exécutés. Cela permet d'exécuter les mêmes instructions pour plusieurs valeurs.

### Java 14

```java
switch(seasonCode) {
	case 0 -> "Spring";
	case 1 -> "Summer";
	case 2 -> "Fall";
	case 3 -> "Winter";
	default -> "???";
}
```
## [[Math]]

# Le priorité des opérateurs

```java
[] . () //l'appel de méthode
! ~ ++ -- +/*一元运算*/ -/*一元运算*/ ()/*cast*/ new
* / %
+ -
<< >> >>>
< <= > >= instanceof
== !=
&
^
|
&&
||
?:
= += -= *= /= %= &= |= ^= <<= >>= >>>=
```
