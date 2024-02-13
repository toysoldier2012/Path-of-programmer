
> [!question] 
> **Q: Quels sont les propriétés de transaction** #D1 
> 
> **Q: Comment assuré ACID** #D2 

## 属性 ACID

### 原子性 Atomicity/Atomicité

Tous les changement apportés aux données sont effectués totalement, ou pas du tout
Il est assuré par undolog

### 一致性 Consistency/Cohérence

Les transactions doivent respecter les contraintes d’intégrité des données de la base de données
Il est assuré par le système de transaction et logique de project

### 隔离性 Isolation

Les transactions(les écritures et lectures) ne seront pas affectées par les autres transactions, qu'elles soient ou non réussies.

- lectures inconsistantes 脏读
	T1读取了一个字段，T2更新了此字段，但没有提交，T1再次读取，字段发生了变化
	使用[[MySQL#^7702a8|READ COMMITTED]]可以解决

- Lectures non répétable 不可重复读
	T1读取了一个字段，T2更新了该字段，T1再次读取该字段，数据发生变
	使用[[MySQL#^6e5ab9|REPEATABLE READ]]可以解决

- Lecture fantôme 幻读
	T1读取了一个表中的某字段，其他事务在该表中插入了一些新数据，T1再次读取就会多出几行
	使用[[MySQL#^2051ad|SERIALIZABLE]]可以解决

Il est assuré par [[MVCC]]

### 持久性 Durability/Durabilité

la durabilité garantit que les transactions réussies survivront de façon permanente et ne seront pas affectées par d’éventuelles pannes ou problèmes techniques
Il est assuré par redolog
