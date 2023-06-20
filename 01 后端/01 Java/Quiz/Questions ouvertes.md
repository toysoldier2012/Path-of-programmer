#### Q: Les caractères de Java POO #oop 
 
- Encapsulation est pour cacher les datas et les méthodes sensitives
- Héritage évide la duplication de code et augmente la réutilisabilité
- Polymorphisme est override

#### Q: Quelles sont les différences entre abstract class et interface #interface #abstract

1.  Les classes abstracts ne peuvent avoir que simple héritage, et les interface peuvent avoir multi héritage
2.  Les classes abstracts peuvent avoir les constructeurs
3.  Les classes abstracts peuvent avoir les attributs
4.  Dans les interfaces, tous les méthodes sont abstracts, après Java 8, les méthodes défaut et les méthodes statiques sont acceptés
5.  Dans les interfaces, avant Java 9, la visibilité de méthode est que public, maintenant il peut être aussi privates et private statique
6.  L'interface est une abstraction d'un comportement spécifique.
7.  La classe abstract est une abstraction d'un type de chose.

#### Q : Les différences entre `String`, `StringBuffer`, `StringBuilder` #string #stringbuffer #stringbuilder 

- `String` 是不可变的
- `StringBuffer` 对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全的。
- `StringBuilder` 更快，线程不安全
- 拼接字符最好不要用 `String + String` 或者  `"chaine1"&&"chaine2"`，过程中会创建 n 个 `StringBuilder`

