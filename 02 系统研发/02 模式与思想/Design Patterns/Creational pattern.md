#pattern

## Singleton
#singleton

Pour assurer qu'un seul instance exist.

Exemple: lire le fichier de configuration; gestion de l'état de système; compteur d'application dans single JVM

1. Lazy
2. Hunger
3. Lazy + Double check
4. Lazy + static class
5. Enum

## Prototype
#prototype

![[Pasted image 20230220224859.png]]

Prototype est pour construire les instances 1 -> N.
Le différence entre prototype et `new`
- Si on a des logiques supplémentaires dans le construction, prototype est plus rapide
- Sinon c'est l'inverse.

## Simple Factory
#simplefactory

![[Pasted image 20231020182506.png]]
## Factory
#factory

![[Pasted image 20231020182618.png]]

## Abstract factory
#abstractfactory

![[Pasted image 20231020182609.png]]

## Builder
#builder 

![[Pasted image 20231020182746.png]]

