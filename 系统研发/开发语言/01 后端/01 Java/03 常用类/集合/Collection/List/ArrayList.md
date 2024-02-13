#arraylist 

# Critères

- Réaliser par `Object[]`
- Non thread-safe
- `null` est autorisé
- La capacité initiale est 10
- La taille de incrémentation est 1.5 (2 avant Java 8) #java8

# Constructeur et méthodes

## Constructeur

```java
ArrayList()
ArrayList(Collection<? extends E> c)
ArrayList(int initialCapacity)
```

## Méthode

[[List#^8575d1]]
```java
//Ajouter

```

[[List#^cffe35]]
```java
//Supprimer
void removeRange(int start, int end) //O(n)
```

[[List#^c73e1c]]
```java
//Modifier
void ensureCapacity(int size);

void trimToSize();
```

[[List#^8e0314]]
```java
//Consulter

```

# Complexité

| Prefix | Insert | Suffix | Remove first | Remove | Remove last | Search by index | Search by value |
| ------ | ------ | ------ | ------------ | ------ | ----------- | --------------- | --------------- |
| O(n)   | O(n)   | O(1)   | O(n)         | O(n)   | O(1)        | O(1)            | O(n)            | 
- Les opérations de dernier élément est O(1)
- Le recherche par index est O(1)