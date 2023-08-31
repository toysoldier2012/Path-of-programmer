#list 

![[Pasted image 20230720170411.png]]

| Utilisation générale | Utilisation spécifique | Gestion des accès concurrents |
| -------------------- | ---------------------- | ----------------------------- |
| [[ArrayList]]        | CopyOnWriteArrayList   | [[Vector]]                    |
| [[LinkedList]]       |                        | Stack                         |
|                      |                        | CopyOnWriteArrayList          |

# Critères

- Collection d'élément ordonnés
- Accepter les doublons
- Accepter les éléments null
- Permettre un accès aux éléments de la liste à partir d'un index

# Constructeur et méthodes

## Constructeur

```java

```

## Méthode

[[Collection#^7ea8a0]]
```java
//Ajouter
boolean add(int index, Object o); //O(n)
boolean addAll(int index, Collection c);
```

^8575d1

[[Collection#^7c777b]]
```java
//Supprimer
E remove(int index) //O(n)
```

^cffe35

[[Collection#^471051]]
```java
//Modifier
default void replaceAll(UnaryOperator<E> operator)

E set(int index, E element) //O(n)

default void sort(Comparator<? super E> c)

List<E> subList(int fromIndex, int toIndex)
//Si la liste originale est modifié(add/remove), le subList lève ConcurrentModificationException lors d'une utilisation de la sous liste
```

^c73e1c

[[Collection#^65180d]]
```java
//Consulter
E get(int index) //O(1) pour ArrayList, O(n) pour LinkedList

int indexOf(Object o) //O(n)
int lastIndexOf(Object o) //O(n)

ListIterator<E> listIterator()
ListIterator<E> listIterator(int index)
```

^8e0314

# Les opérations courants

## Parcourir

1. [[Stream]] 
2. Iterator #iterator
3. Boucle

## Ordonner

1. 可以使用 `Collections` 类的 `sort()` 方法对 `List` 进行排序。

```java
Collection.sort(unsortedList)
```

如果要对自定义对象的列表进行排序，需要确保对象实现了 `Comparable` 接口，并实现了 `compareTo()` 方法，或者在 `sort()` 中指定一个 `Comparator` #comparable #comparator 

``` java
Collections.sort(arrayList, (o 1, o 2) -> o 2.compareTo(o 1));
Collections.sort(arrayList, Comparator.reverseOrder());
```

2. 从 Java 8 开始，`List` 接口提供了一个默认方法 `sort()`，可以直接在列表上进行排序。这种方法要求列表的元素类型实现了 `Comparable` 接口或传入一个自定义的 `Comparator` 对象来定义排序规则。 #comparable #comparator 

```java
unsortedList.sort(null)
unsortedList.sort(Comparator.comparing(String::toString))
```

3. 通过 stream 处理排序

``` java
stream : unsortedList.stream().sorted((s1, s2) -> 	s1.compareTo(s2)).collect(Collectors.toList())
```

## Conversion

### A array

1. `toArray` 方法

```Java
String[] array1 = list.toArray();
```

2. 使用 `stream`

```Java
String[] array2 = list.stream().toArray(String[]::new);
```

### A stream

```java
List<String> list = Stream.of(array).collect(Collectors.toList()); 

List<String> list = Arrays.stream(array).collect(Collectors.toList()); 
```
