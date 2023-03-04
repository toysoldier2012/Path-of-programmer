
1. or = UNION
2. MySQL uses three-valued logic -- TRUE, FALSE and UNKNOWN, <>2 is false and is null is UNKNOWN
3. 
``` SQL
Select c.name as Customers
from Customers c
left join Orders o on o.customerId = c.id
where o.id is null
```
=
```SQL
select customers.name as 'Customers'
from customers
where customers.id not in
(
    select customerid from orders
);
```
4. `IF( condition, [value_if_true], [value_if_false] )` and `ISNULL([value_if_null], [value_if_not_null])`
5. `name NOT REGEXP '^M'` = `name not like 'M%'`
6. 
``` SQL
UPDATE Salary SET sex = (CASE sex WHEN 'm' THEN 'f' ELSE 'm' END)
```
=
```SQL
UPDATE Salary SET sex = IF(sex = 'm', 'f', 'm')
```

7. 
``` SQL
delete p1
FROM Person p1,
    Person p2
WHERE
    p1.Email = p2.Email AND p1.Id > p2.Id
;
```

8. 
```SQL
SUBSTR(string_name , start_index ,end_index)
```

9. 
``` SQL
string_agg(product, ',')
```

10. 
``` SQL
concat(upper(substring(name, 1, 1)), lower(substring(name, 2, len(name))))
```
=
``` SQL
upper(substring(name, 1, 1)) + lower(substring(name, 2, len(name)))
```


11. 
``` SQL
left(name, 1)
```
=
``` SQL
substring(name, 1, 1)
```

12. 
```mssql
UNPIVOT 
```

13. 
``` sql
select t.id,
case
    when t.p_id is null
        then 'Root'
    when t.id in (select at.p_id from tree as at)
        then 'Inner'
    else 'Leaf'
    end as type
from tree t
```


