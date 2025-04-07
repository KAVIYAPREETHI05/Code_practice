## WHERE

 ###  Products with total sales over 200

 ```sql
SELECT product FROM SALES
WHERE SUM(amount)>150
GROUP BY product; //invalid use of group
```
 

## HAVING

 The HAVING clause is used with aggregate functions to filter grouped results.

 ###  Products with total sales over 200

 ```sql
INSERT INTO SALES VALUES(1,'PEN','FAST',100),
(2,'PENCIL','EAST',200),
(3,'PEN','EAST',120),
(4,'ERASER','WEST',80);


SELECT product FROM SALES
GROUP BY product
HAVING SUM(amount)>150;  //pen pencil
```

### Regions where average sales per transaction exceed 90

```sql
SELECT region FROM SALES
GROUP BY region
HAVING AVG(amount)>90;
```

### Count of products sold more than once per region

```sql
SELECT region, product, COUNT(*) AS times_sold
FROM sales
GROUP BY region, product
HAVING COUNT(*) > 1;
```

### Products with total sales between 150 and 400

```sql
SELECT product,SUM(amount) FROM SALES
GROUP BY product
HAVING SUM(amount) BETWEEN 150 AND 400;

```

### Regions with total sales greater than 250

```sql
SELECT region FROM SALES
GROUP BY region
HAVING SUM(amount)>250;
```

### Products with average sale amount less than 100

```sql
SELECT product FROM SALES
GROUP BY product
HAVING AVG(amount)<100;
```

### Products sold in more than one region

```sql
SELECT product,COUNT(DISTINCT region) FROM SALES
GROUP BY product,region
HAVING COUNT(DISTINCT region)>1;
```

### Total number of products sold per region with more than 2 sales
```sql
SELECT region FROM SALES
GROUP BY region
HAVING COUNT(*)>2;
```

### Regions where the minimum sale amount is above 60
```sql
SELECT region FROM SALES
GROUP BY region
HAVING MIN(amount)>60;
```









