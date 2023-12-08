
# QCM

### Alias and GROUP BY error
Language knowledge (60 pts)

You are working with the following table, called `product`: 

| PRODUCT_ID | NAME      |
| ---------- | --------- |
| 1          | High-tech |
| 2          | Food      |
| 3          | Book      |
| 4          | Book      |
| 5          | Book      |
| 6          | Service   |
| 7          | Service   |
| 8          | Service   |
| 9          | Food      |
| 10         | Food      |

The field "NAME" contains the name of the product category, not the name of the product itself.

Which query should you write to count the number of products per category?

- 
```sql
SELECT
	name AS product_category
	,COUNT(product_id)

FROM product

GROUP BY name
```

- 
```sql
SELECT
	name AS product_category
	,COUNT(product_id)

FROM product
```

- 
```sql
SELECT
	name AS product_category
	,COUNT(product_id)

FROM product

GROUP BY product_category
```

- 
```sql
SELECT
	name AS product_category
	,COUNT(product_id)

FROM product

GROUP BY name AS product_category
```

- 
```sql
SELECT
	name AS product_category
	,COUNT(product_id)

FROM product

GROUP BY product_id
```

### JOIN vs subqueries optimization
Language knowledge (40 pts)

You are working with the following tables: 

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

Which query will be the most efficient to calculate the number of products ordered per customer?

- 
```sql
    SELECT
        po.customer_id
        ,COUNT(p.product_id)
    
    FROM
        purchase_order po
        JOIN order_product op ON po.order_id = op.order_id
        JOIN product p ON op.product_id = p.product_id
    
    GROUP BY po.customer_id
    ```
    
- 
```sql
    SELECT
        po.customer_id
        ,COUNT(p.product_id)
    
    FROM
        purchase_order po
        LEFT JOIN order_product op ON po.order_id = op.order_id
        LEFT JOIN product p ON op.product_id = p.product_id
    
    GROUP BY po.customer_id
    
    HAVING COUNT(p.product_id) <> 0
    ```
    
- 
```sql
    SELECT
        po.customer_id
        ,SUM(product_count)
    
    FROM
        purchase_order po
        JOIN (
            SELECT op.order_id, COUNT(op.product_id) AS product_count 
            FROM order_product op 
            GROUP BY op.order_id
        ) op ON po.order_id = op.order_id
    
    GROUP BY po.customer_id
    ```

### Mixing joins
Language knowledge (40 pts)

You are working with the following tables: 

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

What can be said regarding the following joins?

```sql
SELECT
    p.product_id,
    pc.product_category_id,
    op.order_id

FROM
    product p
    JOIN product_category pc ON p.product_category_id = pc.product_category_id
    LEFT JOIN order_product op ON p.product_id = op.product_id  -- LINE 9
    INNER JOIN purchase_order po ON op.order_id = po.order_id  -- LINE 10

WHERE op.order_id IS NOT NULL  -- LINE 12
```

- The code line 10 has the same effect as the code line 12
- The code line 12 has the same effect as changing the `LEFT JOIN` of line 9 into a `INNER JOIN`
- The code line 10 will trigger an error because several types of join are mixed up
- The code line 9 has the same effect as the code line 12

### Mixing joins
Language knowledge (40 pts)

You are working with the following tables: 

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

What can be said regarding the following joins?

```sql
SELECT
    p.product_id,
    pc.product_category_id,
    op.order_id

FROM
    product p
    JOIN product_category pc ON p.product_category_id = pc.product_category_id
    LEFT JOIN order_product op ON p.product_id = op.product_id  -- LINE 9
    INNER JOIN purchase_order po ON op.order_id = po.order_id  -- LINE 10

WHERE op.order_id IS NOT NULL  -- LINE 12
```

- The code line 10 has the same effect as the code line 12
- The code line 12 has the same effect as changing the `LEFT JOIN` of line 9 into a `INNER JOIN`
- The code line 10 will trigger an error because several types of join are mixed up
- The code line 9 has the same effect as the code line 12

### "CASE WHEN" and "GROUP BY" errors
Language knowledge (40 pts)

You are working with the following tables: 

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

You want to compute the number of orders for two product price ranges: 

```sql
SELECT
    CASE
        WHEN p.price < 100 THEN '<100'
        ELSE '>=100'
    ,COUNT(op.order_id)

FROM
    product p
    LEFT JOIN order_product op ON p.product_id = op.product_id
```

Why does the above query generate an error? (There may be more than one reason.)

- The `END` keyword is missing in the `CASE WHEN` syntax
- A `GROUP BY` clause is missing
- A `WHERE` clause is missing
- Another `WHEN` keyword is missing in the `CASE WHEN` syntax
- Another `THEN` keyword is missing in the `CASE WHEN` syntax

### Management of null values
Language knowledge (40 pts)

You are working with the following table, called `product`:

| ID  | TOTAL | QUANTITY |
| --- | ----- | -------- |
| 1  | 0.00  | 4        |
| 2  | 8.00  | 5        |
| 3  | 8.00  | 3        |
| 4  | 0.00  | 0        |
| 5  | 1.00  | 7        |
| 6  | null  | null     |
| 7  | 5.00  | 1        |
| 8  | null  | null     |
| 9  | 2.00  | 1        |
| 10 | 5.00  | 10       |


Select all the queries that return the same output as the following one:  

```sql
SELECT COUNT(total)
FROM product
```

- 
```sql
SELECT COUNT(*)
FROM product
```

- 
```sql
SELECT COUNT(DISTINCT(id))
FROM product
```

- 
```sql
SELECT COUNT(DISTINCT(total))
FROM product
```

- 
```sql
SELECT COUNT(id)
FROM product
WHERE total IS NOT NULL
```

- 
```sql
SELECT SUM(
	CASE WHEN total IS NOT NULL THEN 1
	ELSE 0 END)
FROM product
```

- 
```sql
SELECT COUNT(id)
FROM product
HAVING total IS NOT NULL
```

### "CASE WHEN" location
Language knowledge (40 pts)

In which clauses can you find a `CASE WHEN` syntax?

- `SELECT`
- `FROM`
- `WHERE`
- `GROUP BY`
- `ORDER BY`

### CAST when dividing two integers
Language knowledge (40 pts)

You are working with the following table, called `product`: 

| ID  | TOTAL | QUANTITY |
| --- | ----- | -------- |
| 1   | 0     | 4        |
| 2   | 8     | 5        |
| 3   | 8     | 3        |
| 4   | 3     | 4        |
| 5   | 1     | 7        |
| 6   | null  | null     |
| 7   | 5     | 1        |
| 8   | null  | null     |
| 9   | 2     | 1        |
| 10  | 5     | 10       |

You want to calculate the division between `total` and `quantity` as a decimal number (both fields being stored as integers). 

What should you do?

- Use the following query:
    
    ```sql
    SELECT total / quantity
    FROM product
    ```
    
- Cast either `total` or `quantity` into a decimal number
- Cast `total / quantity` into a decimal number
- Change the default display settings of your database

### "LEFT JOIN" understanding
Language knowledge (20 pts)

You are working with the following tables: 

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

What can be said regarding the following joins?

```sql
SELECT
    p.product_id,
    pc.product_category_id,
    op.order_id
FROM
    product p
    JOIN product_category pc ON p.product_category_id = pc.product_category_id
    LEFT JOIN order_product op ON p.product_id = op.product_id
```

- The query may output some `product_id` without corresponding `order_id`
- The query will only output `product_id` with corresponding `order_id`
- The query may output some `product_id` without corresponding 
    `product_category_id`
- The query will only output some `product_id` with corresponding 
    `product_category_id`

### Alias
Language knowledge (20 pts)

Select the correct statements regarding SQL aliases. 

- It is possible to create a column alias like:
    
```sql
SELECT column_name AS new_column_name
FROM table_name
```

- It is possible to create a table alias like:
    
```sql
SELECT column_name
FROM table_name AS new_table_name
```
    
- SQL aliases are temporary names used during the execution of a specific query
- Giving a table an alias changes the default name of that table
- It is mandatory to give table aliases when joining several tables
- This instruction creates two aliases for the same column name:
    
```sql
SELECT 
  column_name 
  AS new_column_name_1, new_column_name_2
FROM table_name
```

### Count and null values
Language knowledge (20 pts)

You are working with the following table, called `ratings`: 

| id  | rating |
| --- | ------ |
| 1   | 0.47   |
| 2   | null   |
| 3   | 0.77   |
| 4   | 0.41   |
| 5   | null   |
| 6   | 0.97   |
| 7   | 0.65   |
| 8   | null   |
| 9   | 0.05   |
| 10  | 0.59   |

Which querie(s) return the number of rows with non-null rating ? (7 rows in that example).

```sql
SELECT COUNT(rating)
FROM ratings
```
```sql
SELECT COUNT(*)
FROM ratings
```
```sql
SELECT SUM(
	CASE WHEN rating IS NULL THEN 0
	ELSE 1 END)
FROM ratings
```
```sql
SELECT SUM(rating)
FROM ratings
```

### SQL - Foreign key #1
Design (20 pts)

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

From the above database schema, select what best describes the column `customer_id` of the `PURCHASE_ORDER` table.

- Primary key
- Index
- Blob
- Foreign key

### SQL - DROP
Language knowledge (20 pts)

What SQL command is used to remove a table from database?

- DELETE table
- TRUNCATE table
- DROP table
- REMOVE table

### SQL - INSERT
Language knowledge (20 pts)

Which SQL command would you use to add a row in a table of a database?

- INSERT
- ADD
- UPDATE
- MORE

# Text

### WHERE clause with EXISTS keyword

You are working with the following tables: 

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

In the following query, what should you replace `XXX` with, to retrieve the products that have been ordered at least once?

```sql
SELECT p.name
FROM product p
WHERE XXX ( -- Replace XXX 
    SELECT op.product_id
    FROM order_product op 
    WHERE p.product_id = op.product_id
)
```

# Code

### Pivoting columns to rows

#### Data model

 ![](https://static.codingame.com/work/servlet/fileservlet?id=50500557623035)

#### Goal

For data analysis purposes, you want the type of alcohol to appear in rows, not columns.

In other words, instead of three columns (`beer_consumption`, `spirit_consumption`, `wine_consumption`), you want to display two columns: `alcohol` (equal to 'beer', 'spirit' or 'wine') and `alcohol_consumption`. 

#### Requirements

- Expected columns: `country`, `alcohol`, `alcohol_consumption`, in that order.
    
- Sort the rows by `alcohol_consumption` descending, then by `country` ascending. 

#### Example:

| COUNTRY | ALCOHOL | ALCOHOL_CONSUMPTION |
| ------- | ------- | ------------------- |
| Grenada | spirit  | 438                 |
| Namibia | beer    | 376                 |
| Belarus | spirit  | 373                 |
| France  | wine    | 370                 |

### SQL - GROUP BY

![](https://www.codingame.com/work/servlet/fileservlet?id=57161896349644)

Modify the query to list the number of products per product category.
 
Product categories with **no products** are not to be listed.  
  
**Only output the CATEGORY_NAME (product_category.name) and PRODUCT_COUNT columns in that order.**  
 
Example of output:

| CATEGORY_NAME | PRODUCT_COUNT |
| ------------- | ------------- |
| Books         | 3             |
| Automotive    | 2             |
| High-tech     | 8             |

### Exclusions in the JOIN

#### Data model

![](https://static.codingame.com/work/servlet/fileservlet?id=50490099572396)

_`gold`, `silver`, and `bronze` contain the names of athletes who have won medals in the event._ 

#### Goal

Write a query that returns the number of gold medals per swimmer, for swimmers who received **only** gold medals. This means that the swimmer's name will appear in the `gold` column of the `events` table, but not in the `silver` or `bronze` columns.

#### Requirements

- Expected columns: `name`, `total`, in that order.
- Sort the rows by `name` ascending.
- Example:

| NAME           | TOTAL |
| -------------- | ----- |
| Matthew Mccray | 1     |
| Nicole Goldman | 2     |
| Thomas Baker   | 11    |

### Simple WHERE condition (with AND)

#### Data model

![](https://static.codingame.com/work/servlet/fileservlet?id=50338639038339)

#### Goal

Write a query that returns the top _all-around_ baseball hitters. We define a top _all-around_ baseball hitter as someone whose batting average (`ba`) is 0.300 or higher, and whose number of home runs hit (`hr`) is 30 or higher.

#### Requirements

- Expected columns: `first_name`, `last_name`, in that order.
- Sort the rows by `last_name` in alphabetical order. 
- Example:

| FIRST_NAME | LAST_NAME |
| ---------- | --------- |
| Chad       | Adkinson  |
| Vernon     | Giroux    |
| Lewis      | Winters   |




















