#queue 

| Utilisation générale | Utilisation spécifique | Gestion des accès concurrents |
| -------------------- | ---------------------- | ----------------------------- |
| LinkedList           |                        | ConcurrentLinkedQueue         |
| ArrayDeque           |                        | LinkedBlockingQueue           |
| PriorityQueue        |                        | ArrayBlockingQueue            |
|                      |                        | PriorityBlockingQueue         |
|                      |                        | DelayQueue                    |
|                      |                        | SynchronousQueue              |
|                      |                        | LinkedBlockingDeque           |

# 特点

- Collection qui stocke des éléments dans un certain ordre, qu'ils ne soient pas extraites pour traitement
-   `PriorityQueue`: `Object[]` 数组来实现二叉堆
-   `ArrayQueue`: `Object[]` 数组 + 双指针

# 常用方法

![[Pasted image 20231122141756.png]]

![[Pasted image 20231122141855.png]]

![[Pasted image 20231122141818.png]]
