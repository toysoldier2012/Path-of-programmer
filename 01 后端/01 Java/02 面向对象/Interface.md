#interface 

- L'interface est une abstraction d'un comportement spécifique.
- Les seules variables que l'on peut définir dans une interface sont des variables de la classe qui doivent être constantes 
- Toute classe qui implémente cette interface, doit au moins posséder les méthodes qui sont déclarées dans l'interface
- Java 9 之后，方法可以为 `private` 或者 `private static`

### La `default` méthode
#default

- Après Java 8, la méthode `default` permet de définir le comportement dans l'interface auquel elle est définie, elle évide de la redéfinir dans tous les classes d'implémentation 

- Il est possible de créer directement une instance d'une interface si tous les méthodes sont méthodes par défaut
- Une interface fille peut redéfinir la méthode par défaut sans le déclarer par défaut, dans ce cas elle redéfinir comme étant abstraite

- Dans la classe d'implémentation, on rappelle la méthode défaut dans l'interface par `Interface.super.method()

### L'interface locale

Elle ne capture que les variables statics du context englobant

### L'interface fonctionnelle

Elle a qu'une seule méthode abstraite