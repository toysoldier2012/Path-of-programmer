#collection 

![[Pasted image 20230223231319.png]]

# Préambule

1. [[List]]
2. [[Set]]
3. [[Queue]]

# Les méthodes courants

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
