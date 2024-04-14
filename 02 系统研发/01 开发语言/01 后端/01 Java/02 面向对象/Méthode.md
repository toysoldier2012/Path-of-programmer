#method

``` java
modificateurs type_retourné nom_méthode ( arg1, ... ) {... } 
```

# Paramètre
#parameter

## Argument
#argument

La variable transmit en réel dans un paramètre, est un argument

## Référence ou valeur

Si un objet o transmet sa variable d'instance v en paramètre à une méthode m, deux situations sont possibles :

- Si v est une variable primitive alors elle est passée par valeur : il est impossible de la modifier dans m pour que v en retour contienne cette nouvelle valeur.
- Si v est un objet alors m pourra modifier l'objet en utilisant une méthode de l'objet passé en paramètre. 

## Varargs (Les paramètres variable)
#varargs

Elle utilise un notation `...` pour préciser une répétition d'un type d'argument, permet le passage d'un nombre indéfini de paramètres du type précisé.

Tous les paramètres passés sont traités comme un tableau.

# Accesseur et mutateur
#accessor #mutator 
