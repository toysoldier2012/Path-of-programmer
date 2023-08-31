#primitivedatatype

| Type    | Longueur | Valeurs                  | Commentaires                                                           |
| ------- | -------- | ------------------------ | ---------------------------------------------------------------------- |
| boolean | 1 bit    | true ou false            | pas de conversion possible vers un autre type, valeur par défaut false |
| byte    | 8 bits   | -128 à 127               |                                                                        |
| short   | 16 bits  | -32768 à 32767           |                                                                        |
| char    | 16 bits  | `\u0000` à `\uFFFF`      | entouré de cotes simples dans du code Java, valeur par défaut `\u0000` |
| int     | 32 bits  | -2147483648 à 2147483647 |                                                                        |
| float   | 32 bits  |                          | avec un suffix F/f                                                     |
| double  | 64 bits  |                          | sans suffix ou avec un suffix D/d                                      |
| long    | 64 bits  |                          | avec un suffix L/l                                                     |

Trois valeur spéciaux:

```java
Double.POSITIVE_INFINITY
Double.NEGATIVE_INFINITY
Double.NaN
```

0/0 et `Math.sqrt(-1)` est `Double.NaN`

### Java 7

- La valeur des types entiers peut être exprimée dans le système binaire en utilisant le préfixe `0b` ou `0B`

``` java
byte valeurByte = (byte) 0b00010001;
short valeurShort = (short) 0b1001110111101;
int valeurInt = 0b1000;
long valeurLong = 0b010000101000101101000010100010110100001010001011010000101000101 L;
```

- Il est possible d'utiliser un ou plusieurs caractères tiret bas entre les chiffres qui composent un entier littéral

```java
int maValeur = 0b1001110_10001011_01001101_01000101;
long maxLong = 0x7fff_ffff_ffff_ffffL;
```

# [[Conversion#^IgCnnw6f|Conversion]]

## A String

`String.valueOf()` accepte `boolean`, `char`, `double`, `float`, `int`, `long` et `Object`, pour `Object`, la valeur `Object.toString()` sera retourné.


需要注意的是，当将一个较大的整数赋值给 `char` 时，可能会发生截断。因为 `char` 是 16 位的，它只能表示 0 到 65535 范围内的整数值。如果赋值的整数超出了这个范围，将会发生截断，只保留低 16 位的值。 

## Autoboxing/unboxing/Wrapper