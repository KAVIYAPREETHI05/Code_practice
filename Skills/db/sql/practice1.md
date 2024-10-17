### Arithmetic Operations in SQL
```sql
SELECT 10,20,30;  --10 20 30
```
SQL follows the standard order of operations (PEMDAS/BODMAS), which means it will perform multiplication and division before addition and subtraction.
PEMDAS=parenthesis,exponents,multiplication,division,addition,substraction
BODMAS=brackets,orders,division,mulitiplication,addition,subtraction

```sql
SELECT 10+20; --30
```

```sql
SELECT 10+20-15*2/3;  --20
```
### Selecting Specific Columns
```sql
SELECT age,country FROM Customers;  --that particular two columns
```

```sql
SELECT country,age,customer_id FROM Customers;  --orderwise
```

### Using DISTINCT to Remove Duplicates


```sql
SELECT DISTINCT age FROM Customers;  --from(10,20,20,30,20,40) it selects only(10,20,30,40)
```
```sql
SELECT DISTINCT last_name  -- unique last name
FROM Customers;
```

### Filtering with WHERE Clause

```sql
SELECT order_id,amount FROM Orders   
WHERE item='Keyboard';
```

```sql
SELECT *FROM Orders   --all details of orders where item is keyboard
WHERE item='Keyboard';
```

### Using Comparison Operators in WHERE


```sql
SELECT *FROM Orders   --since 400
WHERE amount>=400;
```

```sql
SELECT *FROM Orders
WHERE amount>=400 AND item='Monitor';
```
### Using IN to Match Multiple Values

```sql
SELECT *FROM Orders
WHERE amount>=400 AND item IN ('Keyboard');
```
why this
```sql
SELECT *FROM Orders
WHERE amount>=400 AND item IN ('Keyboard','Monitor');
```

### Using NOT IN to Exclude Values


```sql
SELECT *FROM Shippings
WHERE customer>=3
AND status!='Delivered'; -- exclude
```
(or)
```sql
SELECT *FROM Shippings
WHERE customer>=3
AND status NOT IN ('Delivered');
```
why this
```sql
SELECT *FROM Shippings
WHERE customer>=3
AND status NOT IN ('Delivered','Pending');
```
### Range Queries with BETWEEN
```sql
SELECT *FROM Orders
WHERE amount>=400 AND amount<=800 AND item='Monitor';
```

```sql
SELECT *
FROM Orders
WHERE amount BETWEEN 300 AND 500;
```

### Pattern Matching with LIKE

```sql
SELECT *FROM Orders   -- select all word that statrs with 'key' key board, key chain
WHERE item LIKE 'key %'
```

```sql
SELECT *FROM Orders   -- select all word that ends with 'board' key board, card board
WHERE item LIKE '% board'
```
```sql
SELECT *FROM Orders
WHERE item NOT LIKE ('M%');
```

### Combining Queries with UNION

```sql
SELECT *FROM Shippings
WHERE shipping_id='3' AND status='Delivered'
UNION  -- combines both first and second select
SELECT *FROM Shippings
WHERE customer='1' AND status='Delivered';
```

### Sorting the Result Set with ORDER BY


```sql
SELECT *FROM Orders
ORDER BY amount;
```

```sql
SELECT *FROM Orders
ORDER BY amount DESC;
```
```sql
SELECT *
FROM Orders
ORDER BY -- first 0's then 1's
CASE 
WHEN item IN ('Mouse') THEN 1 --comes at end
ELSE 0
END ASC,
 amount ASC,
 order_id ASC;
```
### Aggregate Functions

```sql
SELECT AVG (amount)
 FROM Orders;
```
### Renaming
```sql
SELECT "item" AS "order item" -- temporary rename
FROM Orders;
```

```sql
ALTER TABLE Orders
RENAME COLUMN "item" TO "order item"; -- permanent rename
```

### Grouping Rows with GROUP BY


```sql
SELECT AVG(amount),customer_id
FROM Orders
GROUP BY customer_id;
```

### Subqueries for Finding Minimum and Maximum


```sql
SELECT *
FROM Orders
WHERE amount=(SELECT MIN(amount) FROM Orders);  -- minimum price
```
```sql
SELECT *
FROM Orders
WHERE amount=(SELECT MAX(amount) FROM Orders); -- maximum price
```








