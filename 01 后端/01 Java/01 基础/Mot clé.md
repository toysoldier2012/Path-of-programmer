#keyword 

- 51 mots clés (keywords) dont 2 ne sont pas utilisés (`const` et `goto`)
- 3 valeurs littérales (literals) : true, false et null

|  |              |            |          |           |           |
| ---------- | ------------ | ---------- | -------- | --------- | --------- |
| abstract   | assert       | boolean    | break    | byte      | case      |
| catch      | char         | class      | const (x) | continue  | default   |
| double     | do           | else       | enum     | extends   | false     |
| final      | finally      | float      | for      | goto (x)   | if        |
| implements | import       | instanceof | int      | interface | long      |
| native     | new          | null       | package  | private   | protected |
| public     | return       | short      | static   | strictfp  | super     |
| switch     | synchronized | this       | throw    | throws    | transient |
| true       | try          | void       | volatile | while     |           |

| Java 9 (les mots réservés dans ficher module) | Java 10 | Java 13 | Java 16 |
| -------------------------------------------- | ------- | ------- | ------- |
| exports                                      | var     | yield   | record  |
| module                                       |         |         |         |
| open                                         |         |         |         |
| opens                                        |         |         |         |
| provides                                     |         |         |         |
| requires                                     |         |         |         |
| to                                           |         |         |         |
| transitive                                   |         |         |         |
| uses                                         |         |         |         |
| with                                         |         |         |         |


### 1.1 Les modificateurs d'accès
#visibility

| Modifier           | Visibility                                       |
| ------------------ | ------------------------------------------------ |
| `private`          | None                                             |
| Sans modificateurs | Classes dans la même package                     |
| `protected`        | Classes dans la même package et les sous-classes |
| `public`           | Partout                                          | 

# Les Mots clés
#keyword

- [[Programmation orientée objet#1.1 Les modificateurs d'accès|Les modificateurs d'accès]] 

- #static 

Elle ne sont définies qu'une seule fois, quel que soit le nombre d'objet instanciés de la class Non-static entity ne peut pas être utilisé dans static méthode

- #final

S'appliquer aux variable, les méthodes ou les classes
- Le référence de variable ne peut plus être changé, mais pour les collections, les contenus est toujours modifiable, si on veut un collection unmodifiable, voir [[Collections#^a35227||Collections]]
- Méthode ne peut plus réécrit
- La sous classe est interdit pour une classe finale

- #instanceof 

Pour déterminer la classe d'un objet, voir aussi [[Variable#Conversion]] 

- #this 

This est un instance d'un objet dans lequel il est utilisé
	
- #super

- #synchronized 

- #volatile 

- #native

Une méthode native est une méthode implémenté en C++, il a la limite de la portabilité, mais avec une vitesse d'exécution plus rapide 

#keyword 

-   module：声明模块的名称和版本。
-   requires：声明模块的依赖项，指定模块所需的其他模块。
-   exports：声明模块的导出包，即该模块的代码可以被其他模块访问的包。
-   opens：声明模块的开放包，即该模块的代码可以被反射访问的包。
-   provides：声明模块的服务实现，即该模块提供的服务接口和实现类。
-   uses：声明模块的服务使用，即该模块使用的服务接口。
-   with：在提供服务时使用，指定服务实现的附加提供者。