#arraylist 

# Critères

- Réaliser par `Object[]`
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

```java
//Ajouter
boolean add(Object o); //O(1)
boolean addAll(Collection c);
boolean addAll(int index, Collection c);
```

```java
//Supprimer
void clear();

Object remove(int index); //O(n)
void removeRange(int start, int end) //O(n)
```

```java
//Modifier
void ensureCapacity(int size);

Object set(int index, Object o); //O(n)

void trimToSize();
```

```java
//Consulter
Object get(int index); //O(1)

int indexOf(Object o); //O(n)
int lastIndexOf(Object o); //O(n)

boolean isEmpty();
int size();
```

# Complexité

| Prefix | Insert | Suffix | Remove first | Remove | Remove last | Search by index | Search by value |
| ------ | ------ | ------ | ------------ | ------ | ----------- | --------------- | --------------- |
| O(n)   | O(n)   | O(1)   | O(n)         | O(n)   | O(1)        | O(1)            | O(n)            | 
- Les opérations de dernier élément est O(1)
- Le recherche par index est O(1)