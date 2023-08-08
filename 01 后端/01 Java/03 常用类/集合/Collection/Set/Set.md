#set

| Utilisation générale | Utilisation spécifique | Gestion des accès concurrents |
| -------------------- | ---------------------- | ----------------------------- |
| [[HashSet]]              | CopyOnWriteArraySet    | CopyOnWriteArraySet           |
| [[TreeSet]]              | EnumSet                | ConcurrentSkipListSet         |
| [[LinkedHashSet]]        |                        |                               |

![[Pasted image 20230808122537.png]]

# Critères

- L'ordre et null accept selon l'implémentation
- N'accepte pas doublons
- Les éléments ajoutées doivent réimplémenter leur méthodes `equals()` et `hashCode()` 

# Constructeur et méthodes

## Méthode

```java
//Ajouter
boolean add(E e)
boolean addAll(Collection c)

```

```java
//Supprimer
void clear()
boolean remove(Object o)
```

```java
//Modifier

```

```java
//Consulter
boolean contains(Object o)
boolean containsAll(Collection c)

boolean equals(Object o) 
//Comparer le type Set, nombre des éléments et chaque élément

boolean isEmpty()
Iterator iterator()

```
