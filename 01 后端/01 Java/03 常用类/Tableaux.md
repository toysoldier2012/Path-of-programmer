#array 

# Déclaration et allocation

``` Java
int tableau[] = new int[50]; // déclaration et allocation
int[] tableau = new int[50];
int tab[];         // déclaration
tab = new int[50]; // allocation

float tableau[][] = new float[10][10];
int dim1[][] = new int[3][];
dim1[0]      = new int[4];
dim1[1]      = new int[9];
dim1[2]      = new int[2];
```

# L'initialisation

```java
int tableau[5]    = {10, 20, 30, 40, 50};
int tableau[3][2] = {{5, 1}, {6, 2}, {7, 3}};
int tableau[] = {10, 20, 30, 40, 50};
int[][] tabEntiers = {{1, 2, 3, 4, 5, 6}, {1, 2, 3, 4}, {1, 2, 3, 4, 5, 6, 7, 8, 9}};
int[] i1 = new int[]{1,2,3,4,5,7,8};
```

# Parcours

- [[Stream]]

```java
Arrays.stream(arr).forEach(System.out::println)
```

- [[Hello Java#^6c83db|Boucle]]

# [[Conversion#^Ll6DJAsT||Conversion]]

## 1. Tableau à Stream

```java
Arrays.stream(array)
```

Que pour les types de `int[]`, `long[]`, `double[]`, ou `T extends Object[]` contenir les types boxed