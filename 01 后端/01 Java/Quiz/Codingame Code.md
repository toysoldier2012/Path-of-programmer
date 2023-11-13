![[Pasted image 20231112111844.png]]
![[Pasted image 20231112111914.png]]
![[Pasted image 20231112111950.png]]
![[Pasted image 20231112112008.png]]

### A mysterious diary
#easy

![[Pasted image 20231112112117.png]]

### Abstraction
#easy

![[Pasted image 20231112112139.png]]

### Add some drama to a string

### Anagrams
#easy

![[Pasted image 20231112112240.png]]

### Approximation of π

![[Pasted image 20231112112301.png]]

### ASCII Art

![[Pasted image 20231112112322.png]]

### Autumn leaves

### Bacteria

### Bad calculator

### Best Profit Sequence

### Blood type

### Browse a graph to buy school supplies for your kids

### Buying Shirts

### Calculating a bounding rectangle

### Check a sudoku grid (and output the first error)
#middle

Trouver la relation entre i, j et les coordonnées

![[Pasted image 20231112112505.png]]

### Check a sudoku grid (simple)
#middle

跟上面的差不多，不用返回 invalide 的情况

### Check digit computation
#easy 

Char to int, '3' - '0'

![[Pasted image 20231112112546.png]]

### City Travel

### Combination options in a tournament

### Compute the "size on disk" of a file
#easy 

You may have noticed that files have two sizes. The "file size" and the "size on disk", which is always greater or equal than the file size. Storage media are divided into "clusters". A file can occupy many clusters, but a cluster can only be allocated to one single file. The "size on disk" corresponds to the total size of all the clusters allocated to that file. Given the cluster size of a disk and a file size, compute its size on disk. 
Example 
• A disk has a cluster size of 512 bytes. 
• A file has a size of 1500 bytes. 
• 2 clusters (512^ * 2 = 1024brtes ) would not be enough to store this file. 4 clusters (2048 bytes) would be too much, one of the cluster would be empty. 
The correct number of clusters is 3. 
• The total size of these clusters is (512^ * 3 = 1536bytes ), which is the size on disk of this file.
### Convert bytes to Kibibytes or Mebibytes
#easy 
### Count-quarium

### Counter synchronization

### Design pattern 02

### Different digits

### Duodigits
#easy 

Considérer les chiffres négatifs

![[Pasted image 20231112114220.png]]

### Duplicates removal
#easy

![[Pasted image 20231112114251.png]]

### Eat what you can. Pay what you want.

### Enchanted land of Evenaria
#easy

Dans le pays enchanté d'Evenaria, une elfe nommé Codelia était à la recherche des mystérieuses "Pierres paires", qui maintenaient l'équilibre et l'harmonie. 
Un jour, elle découvrit un parchemin ancien contenant une liste de numéros représentant leurs emplacements. 
Cependant, le parchemin était endommagé et tous les nombres semblaient mélangés. 
Codelia demanda de l'aide à un vieux et sage hibou, qui lui conseilla d'inverser la liste et de ne conserver que les nombres pairs, afin de révéler la séquence originale des pierres. 
Désormais, il vous appartient d'aider Codelia à déchiffrer ce parchemin en écrivant un sortilège qui exécute cette opération. 
Implémentation Fonction Implémenter la méthode spell. 
Paramètres 
numbers (`List<Integer>`): Une liste de nombre entiers 
Valeur de retour enchantedNumbers (`List<Integer>`): La liste inversée, avec uniquement les nombres pairs 

### Exception
#easy 

![[Pasted image 20231112114409.png]]

### File finder
#hard

![[Pasted image 20231112114430.png]]

### Finding The Largest Profit
#hard 

Kadane's algorithm

![[Pasted image 20231112114448.png]]

### FizzBuzz
#easy 

Fizz buzz is a group word game for children to teach them about division.Players take turns to count incrementally, replacing any number divisible by three with the word "fizz", and any number divisible by five with the word "buzz", and any number divisible by both 3 and 5 with the word "fizzbuzz".

### Follow the path on a 2D grid
#todo 

???????????????

Vous avez une liste de chaînes de caractères représentant une grille en deux dimensions. 
Le premier caractère de la première chaîne correspond au coin supérieur gauche, de coordonnées (0, 0).
La grille a toujours la même taille : 
- Largeur = 15 (chaque chaîne contient 15 caractères) 
- Hauteur = 10 (il y a 10 chaînes dans la liste) 
La grille contient un chemin unique, composé d'étoiles (caractère et de lettres minuscules). 
Le chemin commence toujours aux coordonnées (0, 0), et ne contient ni fourche ni boucle. 
Il peut avancer dans les quatre directions (haut, droite, bas, gauche), mais pas en diagonale. 
Vous devez suivre le chemin et enregistrer les lettres dans l'ordre où vous les rencontrez (n'enregistrez pas les étoiles). 
A la fin du parcours, renvoyez la chaîne constituée par les lettres.
Le chemin peut commencer immédiatement par une lettre, et peut aussi se terminer par une lettre. 
Le chemin a une longueur minimale de deux caractères et contient au moins une lettre. 

```java
Import java. Util.*;

Public class Main {
    Public static void main (String[] args) {
        List<String> grid = Arrays.AsList (
            "***",
            "**c**od**i**",
            //... D'autres lignes si nécessaire
        );
        System.Out.Println (followPathAndCollectLetters (grid));
    }

    public static String followPathAndCollectLetters (List<String> grid) {
        StringBuilder letters = new StringBuilder ();
        Int x = 0, y = 0;
        
        // Directions possibles [up, right, down, left] dans [y, x]
        int[][] directions = {{-1, 0}, {0, 1}, {1, 0}, {0, -1}} ;
        
        While (true) {
            Boolean pathFound = false;
            For (int[] direction : directions) {
                Int newY = y + direction[0];
                Int newX = x + direction[1];
                
                // Vérification si la nouvelle position est dans la grille
                if (newY >= 0 && newY < grid.size() && newX >= 0 && newX < grid.Get (newY). Length ()) {
                    Char nextChar = grid.Get (newY). CharAt (newX);
                    
                    // Vérification si la nouvelle position fait partie du chemin
                    If (nextChar == '*' || Character.IsLowerCase (nextChar)) {
                        Y = newY;
                        X = newX;
                        
                        // Ajouter la lettre si c'est une
                        If (Character.IsLowerCase (nextChar)) {
                            Letters.Append (nextChar);
                        }
                        
                        PathFound = true;
                        Break;
                    }
                }
            }
            
            // Sortie de la boucle si aucun chemin trouvé
            If (! PathFound) {
                Break;
            }
        }
        
        Return letters.ToString ();
    }
}
```

### From the fruit we know the tree
#middle 

Recursion et iteration

### Function parsing

### Giving change

![[Pasted image 20231112115857.png]]

### Group bytes by chunks, then calculate the checksums

貌似有

### Hack PayPaul!

### Hello World

```bash
console> java Echo Hello you ! 
Hello
you
! 
console> 
```

Écrivez le programme

```java
Public class Echo {
    Public static void main (String[] args) {
        For (String arg : args) {
            System.Out.Println (arg);
        }
    }
}
```

### Image filters

### Immutable object using a Date

### Inheritance - Use of the "extends" keyword

![[Pasted image 20231112120232.png]]

### Inner matrix

### Intervals

![[Pasted image 20231112120304.png]]

### Javanais

![[Pasted image 20231112120326.png]]

### Joining point

![[Pasted image 20231112120349.png]]

### Kid addition check

### Largest wins from chaos

![[Pasted image 20231112120421.png]]

### Loop detection

![[Pasted image 20231112120457.png]]

### Magic Stones

### Memory leak on a stack

### Move towards zero

![[Pasted image 20231112120540.png]]

### Multiply ingredient quantities of a recipe

You have the ingredient list of a one-person recipe. 
You want to cook it for many persons (defined by nbPersons). 
So, you must multiply all the quantities. 
The ingredient list consists of strings, each defining a specific product. 
They all have the following format: 
• An integer (written with digits), defining the quantity. A space character. 
• Some words, defining the product. 
Modify the string by multiplying the initial integer by nbPersons 
You do not have to take care of the singular/plural of the words defining the product. 
These words may contain some numbers, you must not modify them. 
The order of the lines must be preserved. 

Example You want to cook a cake for 3 persons. Here is the initial ingredient list for one person: 2 eggs 200 grams of flour 150 grams of sugar 1 liter(s) of milk You must output this list: 6 eggs 688 grams of flour 450 grams of sugar 3 liter(s) of milk

### Packing Suitcases

### Portals

### Pyramid

????????

### Range Sum

### Rebuilding a message

???????????

### Red envelopes

![[Pasted image 20231112121019.png]]

### Reshape String

![[Pasted image 20231112121039.png]]

### Rotating table

### Sand Pile

### Score Optimization

### Secret messages confiscated from your pupils

### Secure closure of an I/O stream

![[Pasted image 20231112121150.png]]

### Simple boolean expression

![[Pasted image 20231112121209.png]]

### Simple encoding

![[Pasted image 20231112121231.png]]

### Simple fix

![[Pasted image 20231112121257.png]]

### Stock Prices

![[Pasted image 20231112121325.png]]

### String parser

Xxxxx?

### Strings equality

Is foo?

### Sum Pairs

![[Pasted image 20231112121421.png]]

### Summer Sales

![[Pasted image 20231112121441.png]]

### Summing based on factors

![[Pasted image 20231112121458.png]]

### Tennis Game

![[Pasted image 20231112121514.png]]

### The dancer

### The Macaron Shop

### The trick of mixing the letters inside a word

### Threads communication

### Use of string buffers/join

![[Pasted image 20231112121609.png]]

### Where are the Higgs bosons?

### Word Filtering

![[Pasted image 20231112121705.png]]

### Word Frequencies

![[Pasted image 20231112121728.png]]


# Achieve

Objectif Déplacer un atome sur une grille à l'aide d'actions prédéfinies. ✓ Règles Vous avez découvert d'anciens procédés alchimiques permettant de transmuter la matière. Vous pouvez ajouter ou retirer des protons et des neutrons à un atome. Votre atome est placé dans l'aire de jeu. L'axe des abscisses représente le nombres de protons et l'axe des ordonnées le nombre de neutrons. Vous devez lister les actions à effectuer afin que l'atome atteigne le nombre attendu de protons et de neutrons. Vous disposez des 3 actions prédéfinies suivantes : PROTON: ajoute un proton à l'atome. Dans l'aire de jeu, cela équivaut à le déplacer d'une case vers la droite. NEUTRON : ajoute un neutron, déplace l'atome d'une case vers le bas. ALPHA]: retire deux protons et deux neutrons par désintégration alpha, déplace l'atome de deux cases en diagonale vers la gauche et le haut. Vous devez renvoyer une liste de chaîne de caractère correspondant aux actions à effectuer. Par exemple, si vous renvoyez une liste contenant les mots ALPHA", "PROTON PROTON" PROTON, Fatome perdra deux protons et deux neutrons, puis regagnera 3 protons. Au final, il se déplacera de deux cases vers le haut et une case vers la droite. L'ordre des actions n'a pas d'importance. Il n'est pas obligatoire de minimiser le nombre d'actions. Votre atome peut être déplacé en dehors de la grille, y compris vers le haut et vers la gauche. Implémentation Implémentez la méthode solve (protonsStart, neutronsStart, protonsTarget, neutronsTarget)] Cette méthode doit retourner une liste de chaînes de caractères : les actions successives à effectuer pour passer de l'atome fourni à l'atome cible. La méthode prend 4 paramètres d'entrée: protonsStart et neutronsStart représentent le nombre de protons et de neutrons de T'atome initial. protonsTarget et neutronsTarget représentent le nombre de protons et de neutrons de l'atome souhaité. Conditions de Victoire Votre liste d'actions déplace correctement l'atome, jusqu'au nombre souhaité de protons et de neutrons. Conditions de Défalte • Votre programme indique une action invalide. ⚫ La liste d'actions retournée par votre méthode ne déplace pas fatome au bon endroit. Votre liste dépasse 1000 actions.

```java
Import java. Util. ArrayList;
Import java. Util. List;

Public class AtomMover {
    
    public static List<String> solve(int protonsStart, int neutronsStart,
                                     int protonsTarget, int neutronsTarget) {
        List<String> actions = new ArrayList<>();

        int protonDiff = protonsTarget - protonsStart;
        int neutronDiff = neutronsTarget - neutronsStart;

        while (Math.abs(protonDiff) >= 2 && Math.abs(neutronDiff) >= 2) {
            if (protonDiff < 0 && neutronDiff < 0) {
                actions.add("ALPHA");
                protonDiff += 2;
                neutronDiff += 2;
            } else {
                break;
            }
        }

        while (protonDiff != 0 || neutronDiff != 0) {
            if (protonDiff > 0) {
                actions.add("PROTON");
                protonDiff--;
            } else if (protonDiff < 0) {
                actions.add("ALPHA");
                protonDiff += 2;
                neutronDiff += 2;
            }

            if (neutronDiff > 0) {
                actions.add("NEUTRON");
                neutronDiff--;
            }
        }
        
        // Vérification de la taille de la liste d'actions.
        if (actions.size() > 1000) {
            throw new IllegalArgumentException("La liste d'actions dépasse 1000.");
        }

        return actions;
    }

    // Exemple d'utilisation
    public static void main(String[] args) {
        int protonsStart = 10;
        int neutronsStart = 10;
        int protonsTarget = 5;
        int neutronsTarget = 8;
        List<String> actions = solve(protonsStart, neutronsStart, protonsTarget, neutronsTarget);
        System.out.println(actions);
    }
}
```

complétez la méthode isTwin(a, b) dont a et b sont deux valeurs string, retourne True si a et b auront les mêmes caractères sans compter l'ordre. Exemple 'Romain' et 'Marion' => true in javascript

```java
function isTwin(a, b) {
    // Vérifier d'abord si les deux chaînes ont la même longueur
    if (a.length !== b.length) {
        return false;
    }

    // Convertir les chaînes en tableaux de caractères et les trier
    const sortedA = Array.from(a).sort().join('');
    const sortedB = Array.from(b).sort().join('');

    // Comparer les deux chaînes triées
    return sortedA === sortedB;
}

// Exemple d'utilisation :
const result = isTwin('Romain', 'Marion');
console.log(result); // true
```




