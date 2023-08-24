#primitivedatatype

| Type    | Désignation                                   | Longueur | Valeurs                                    | Commentaires                                                           |
| ------- | --------------------------------------------- | -------- | ------------------------------------------ | ---------------------------------------------------------------------- |
| boolean | valeur logique : true ou false                | 1 bit    | true ou false                              | pas de conversion possible vers un autre type, valeur par défaut false |
| byte    | octet signé                                   | 8 bits   | -128 à 127                                 |                                                                        |
| short   | entier court signé                            | 16 bits  | -32768 à 32767                             |                                                                        |
| char    | caractère Unicode                             | 16 bits  | `\u0000` à `\uFFFF`                        | entouré de cotes simples dans du code Java, valeur par défaut `\u0000` |
| int     | entier signé                                  | 32 bits  | -2147483648 à 2147483647                   |                                                                        |
| float   | virgule flottante simple précision (IEEE 754) | 32 bits  | 1.401 e-045 à 3.40282 e+038                  | avec un suffix f, par exemple 2 f                                     |
| double  | virgule flottante double précision (IEEE 754) | 64 bits  | 2.22507 e-308 à 1.79769 e+308                | avec un suffix d, par exemple 2 d                                     | 
| long    | entier long                                   | 64 bits  | -9223372036854775808 à 9223372036854775807 |                                                                        |

> [!question] 
> 请注意，这些长度是 Java 规范中定义的标准长度，但具体的实现可能会有所不同。此外，还有其他与平台相关的整数类型（如 `char` 的无符号版本 `char`）和大数字类型（如 `BigInteger` 和 `BigDecimal`），它们的长度可以根据具体的库和需求而变化。 

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
