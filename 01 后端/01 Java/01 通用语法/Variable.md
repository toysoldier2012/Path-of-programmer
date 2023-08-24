#variable 

# 类型

## 1. [[Type primitif]]

## 2. [[String]]

## 3. [[Tableaux]]

## 4. Objet

## 5. 其他常见类型

### `BigDecimal` / `BigInteger`

- La classe `BigDecimal` permet de réaliser de tels calculs du type numérique flottant, en permettant d'avoir le contrôle sur la précision
- Il est préférable d'utiliser le constructeur attendant en paramètre la valeur sous forme de chaîne de caractères.

# [[Conversion]]

> [!info] 
> 需要注意的是，当将一个较大的整数赋值给 `char` 时，可能会发生截断。因为 `char` 是 16 位的，它只能表示 0 到 65535 范围内的整数值。如果赋值的整数超出了这个范围，将会发生截断，只保留低 16 位的值。 

## 6 . 强制转换 
#cast 

^3367ba

# Autoboxing/unboxing/Wrapper
