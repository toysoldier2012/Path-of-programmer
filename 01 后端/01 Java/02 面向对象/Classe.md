#class 

# Entité

1. Déclaration
	- en format CamelCase

2. Constructeur
	- en format CamelCase

4. [[Methode]]
	- en format camelCase

6. block

# Classe spécifique

- Classe abstract

- [[Interface]]

> [!question] 
>  Q: Quelles sont les différences entre abstract class et interface #D1 
>  1. Les classes abstracts ne peuvent avoir que simple héritage, et les interface peuvent avoir multi héritage
>  2. Les classes abstracts peuvent avoir les constructeurs
>  3. Les classes abstracts peuvent avoir les attributs
>  4. Dans les interfaces, tous les méthodes sont abstracts, après Java 8, les méthodes défault et les méthodes statiques sont acceptés, après Java 9, elles peuvent avoir les méthodes privates et private statique
>  5. Dans les interfaces, avant Java 8, la visibilité de méthode est que public, maintenant il peut être aussi private
>  6. L'interface est une abstraction d'un comportement spécifique.
>  7. La classe abstract est une abstraction d'un type de chose.

- 内部类

- 匿名内部类
#anonymousclass 

``` java
abstract class Animal {
    abstract void makeSound();
}

interface Jumpable {
    void jump();
}

public class Main {
    public static void main(String[] args) {
        // Creating an anonymous class that extends the Animal class and implements the Jumpable interface
        Animal animal = new Animal() {
            @Override
            void makeSound() {
                System.out.println("Meow");
            }
        };
        
        Jumpable jumper = new Jumpable() {
            @Override
            public void jump() {
                System.out.println("Jumping high!");
            }
        };
        
        // Calling methods on the anonymous classes
        animal.makeSound();  // Output: Meow
        jumper.jump();  // Output: Jumping high!
    }
}
```

# Mot clé
#keyword

- [[Programmation orientée objet#^683229|Règles de visibilité]]
- static ^a56f3a
- final
	只能在构造器，初始化块，声明是赋值
- abstract
- native
	使用 native 关键字说明这个方法是原生函数，也就是这个方法是用 C/C++语言实现的，并且被编译成了 DLL，由 java 去调用

- synchronized
- volatile
	共享变量

- transient
	不需要序列化

- this
- super

# `==` 和 `equals()` 的区别

## `==`

-   对于基本数据类型来说，`==` 比较的是值。
-   对于引用数据类型来说，`==` 比较的是对象的内存地址。

## `equals()` 

-   **类没有重写 `equals()`方法** ：通过`equals()`比较该类的两个对象时，等价于通过`==`比较这两个对象，使用的默认是 `Object`类`equals()`方法。
-   **类重写了 `equals()`方法** ：一般我们都重写 `equals()`方法来比较两个对象中的属性是否相等；若它们的属性相等，则返回 `true`(即，认为这两个对象相等)。

String重写了`equals()`方法

## `hashCode()`
^c9d876

``` Java
public native int hashCode();
```

相同的对象`hashCode`一定相同，反之不然，所以在将对象加入`hashSet`中时，先对比`hashCode`，如果一致，再调用`equals()` ，以确定对象是否真的一致

如果重写 `equals()` 时没有重写 `hashCode()` 方法的话就可能会导致 `equals` 方法判断是相等的两个对象，`hashCode` 值却不相等。


