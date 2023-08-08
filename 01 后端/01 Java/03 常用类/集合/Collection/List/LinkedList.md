#linkedlist 

# Critères

- Réaliser par la liste double chainé
- Une ensemble de [[Node]]
- Contient trois élément important Node head, Node tail, et length
- Non synchronisé.

# Constructeur et méthodes

## Constructeur

```java
LinkedList()
LinkedList(Collection c)
```

## Méthode

[[List#^8575d1]]
```java
//Ajouter
void addFirst(E e)
void addLast(E e)
```

[[List#^cffe35]]
```java
//Supprimer
E pollFirst()
E pollLast()
```

[[List#^c73e1c]]
```java
//Modifier

```

[[List#^8e0314]]
```java
//Consulter
E getFirst()
E getLast()

E peekFirst()
E peekLast()
```


# Complexité

| Prefix | Insert | Suffix | Remove first | Remove | Remove last | Search by index | Search by value |
| ------ | ------ | ------ | ------------ | ------ | ----------- | --------------- | --------------- |
| O(1)   | O (n)   | O(1)   | O(1)         | O (n)   | O (1)        | O (n)            | O (n)            | 
