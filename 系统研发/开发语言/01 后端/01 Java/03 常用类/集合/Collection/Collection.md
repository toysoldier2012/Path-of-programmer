#collection 

![[Pasted image 20230223231319.png]]

# Préambule

1. [[List]]
2. [[Set]]
3. [[Queue]]

# Critères

- 

# Constructeur et méthodes

## Constructeur

```java

```

## Méthode

```java
//Ajouter
boolean add(Object o); //O(1)
boolean addAll(Collection c);
```

^7ea8a0

```java
//Supprimer
void clear();

boolean remove(Object o)
boolean removeAll(Collection<?> c)
```

^7c777b

```java
//Modifier
boolean retainAll(Collection c)

default Stream<E> parallelStream()
default Stream<E> stream()

Object[] toArray()
<T> T[] toArray(T[] a)
```

^471051

```java
//Consulter
boolean contains(Object o) //O(n)
boolean containsAll(Collection<?> c)

boolean equals(Object o)
//Retourner true, si les deux lists ont la meme taille et tous les éléments correspondants sont pareil

boolean isEmpty()

Iterator<E> iterator()

int size()
```

^65180d

Certains méthodes des sous types lèvent `UnsupportedOperationException` car leur implémentation est optionnelle

## Create

```Java
boolean add(E e)
boolean addAll(Collection<? extends E> c)
```

## Research

```Java
boolean contains(Object o)
boolean containsAll(Collection<?> c)
boolean isEmpty()

Iterator<E> iterator()

int size()
```

## Delete

```Java
void clear()

boolean remove(Object o)
boolean removeAll(Collection<?> c)
default boolean removeIf(Predicate<? super E> filter)

boolean retainAll(Collection<?> c)
```

## Transformer

```java
Object[] toArray()
<T> T[] toArray(T[] a)

default Stream<E> stream()
default Stream<E> parallelStream()
```
