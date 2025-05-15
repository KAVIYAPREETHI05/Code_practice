## SELECT
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
## WHERE
```sql
SELECT *FROM Orders 
WHERE amount>300;
```

```sql
SELECT *FROM Orders 
WHERE item LIKE 'M%';
```
```sql
SELECT *FROM Orders 
WHERE item LIKE '%a';
```
```sql
SELECT * FROM employees WHERE email NOT LIKE '%@bitsathy.ac.in';
```

```sql
SELECT *FROM Orders 
WHERE amount BETWEEN 300 AND 1200;   -- 300 included but 1200 is not included
```
```sql
SELECT *FROM Shippings 
WHERE shipping_id>3 AND customer>3;
```

```sql
SELECT *FROM Orders 
WHERE amount IS NOT NULL;
```
```SQL
SELECT *FROM Orders 
WHERE item IS NOT 'Monitor';
```

```sql
SELECT *FROM Orders 
WHERE item IN ('Keyboard','Monitor');
```

```sql
SELECT * FROM Orders
WHERE  date_ <'2005-02-19';
```
```sql
SELECT * FROM Orders
WHERE date_ BETWEEN NOW() - INTERVAL 1 MONTH AND NOW();  -- last one  month

```

## DISTINCT


DISTINCT will treat NULL as a distinct value, so only one NULL will be returned even if there are multiple NULL values in the column.


```sql
SELECT DISTINCT * FROM Orders;
```
```sql
SELECT DISTINCT amount FROM Orders;
```
```sql
SELECT COUNT(DISTINCT amount) FROM Orders;
```
```sql
SELECT SUM(DISTINCT amount) FROM Orders;

```
```sql
SELECT DISTINCT City FROM Customers ORDER BY City ASC;

```
```sql
SELECT DISTINCT amount FROM Orders WHERE date_ IS NOT NULL;
```
```sql
SELECT DISTINCT YEAR(OrderDate) FROM Orders;
```
```sql
SELECT DISTINCT Country FROM Customers GROUP BY Country;

```

###  Write a SQL query to fetch "FIRST_NAME" from the Student table in upper case and use ALIAS name as STUDENT_NAME.
```sql
SELECT upper(FIRST_NAME) FROM STUDENT AS STUDENT_NAME;
```

### Write a SQL query to fetch unique values of MAJOR Subjects from Student table.
```SQL
SELECT DISTINCT MAJOR FROM STUDENT;
```

### Write a SQL query to print the first 3 characters of FIRST_NAME from Student table.

```SQL
SELECT SUBSTRING(FIRST_NAME,1,3) FROM STUDENT;
```

###  Write a SQL query to find the position of alphabet ('a') int the first name column 'Shivansh' from Student table.

```sql
SELECT INSTR(FIRST_NAME, 'a') FROM Student WHERE FIRST_NAME = 'Shivansh';

```

### to find all occurence of 

```sql
SELECT LENGTH(FIRST_NAME) - LENGTH(REPLACE(FIRST_NAME, 'R', '')) AS R_COUNT
FROM STUDENT
WHERE FIRST_NAME = 'Radha';

```
or

```sql
SELECT 
CASE 
	WHEN INSTR(FIRST_NAME,'a')=0 THEN 0
    ELSE LENGTH(FIRST_NAME)- INSTR(REVERSE(FIRST_NAME),'a')+1
END AS last_occurrence
FROM Student;
```

### Write a SQL query to print the FIRST_NAME and LAST_NAME from Student table into single column COMPLETE_NAME.

```sql
SELECT CONCAT(FIRST_NAME,LAST_NAME) FROM STUDENT  AS COMPLETE_NAME;
```
### Write a SQL query to print all Student details from Student table order by FIRST_NAME Ascending and MAJOR Subject descending .

```sql
SELECT *FROM STUDENT
ORDER BY FIRST_NAME ASC, MAJOR DESC;
```

###  Write a SQL query to print details of the Students with the FIRST_NAME as 'Prem' and 'Shivansh' from Student table.

```sql
SELECT * from Student WHERE FIRST_NAME IN ('Prem' , 'Shivansh');
```

###  Write a SQL query to print details of the Students with the FIRST_NAME not as 'Prem' and 'Shivansh' from Student table.

```sql
SELECT * from Student WHERE FIRST_NAME NOT IN ('Prem' , 'Shivansh');
```

### Write an SQL query to print details of the Students whose FIRST_NAME ends with ‘a’ and contains five alphabets.

```sql
SELECT * FROM Student WHERE FIRST_NAME LIKE '_____a';
```
###  Write an SQL query to print details of the Students whose GPA lies between 9.00 and 9.99.

```SQL
SELECT *FROM STUDENT
WHERE GPA BETWEEN 9.00 AND 9.99;
```

###  Write a SQL query to print FIRST_NAME from the Student table after replacing 'a' with 'A'.

```SQL
SELECT REPLACE(FIRST_NAME,'a','Z') FROM STUDENT;
```

### Write an SQL query to fetch the count of Students having Major Subject ‘Computer Science’.

```sql
SELECT COUNT(MAJOR) FROM student
WHERE MAJOR='Computer Science'
```

### Write an SQL query to fetch Students full names with GPA >= 8.5 and <= 9.5.

```SQL
SELECT CONCAT(FIRST_NAME,LAST_NAME) AS FULL_NAME FROM STUDENT
WHERE GPA >=8.5 AND GPA<=9.5;
```

###  Write an SQL query to fetch the no. of Students for each MAJOR subject in the descending order.
```SQL
SELECT MAJOR,COUNT(MAJOR) FROM STUDENT
GROUP BY MAJOR
ORDER BY COUNT(MAJOR) DESC;
```

### Write an SQL query to show only odd rows from Student table.
```sql
SELECT * FROM Student WHERE student_id % 2 != 0;
```

```sql
SELECT *FROM (
SELECT * ,ROW_NUMBER() OVER() AS row_num FROM STUDENT
)AS numbered
WHERE row_num%2!=0;
```

### Write an SQL query to show the top n (say 5) records of Student table order by descending GPA.
```SQL
SELECT *FROM STUDENT
ORDER BY GPA DESC
LIMIT 4,1;   --  //LIMIT 1 OFFSET 4;
```

### Write an SQL query to determine the 5th highest GPA without using LIMIT keyword.
```sql
SELECT *FROM (
SELECT GPA,ROW_NUMBER() OVER(ORDER BY GPA DESC) AS ROW_NUM FROM STUDENT
)AS NUMBERED 
WHERE ROW_NUM=5;
```

### Write an SQL query to fetch the list of Students with the same GPA.
```SQL
SELECT *FROM student
WHERE GPA IN(
SELECT GPA
    FROM student
    GROUP BY GPA
    HAVING COUNT(*) > 1
    );
```

### Write an SQL query to show the second highest GPA from a Student table using sub-query.
```SQL
SELECT MAX(GPA) AS second_max FROM student 
WHERE GPA!=(
SELECT MAX(GPA) AS first_max FROM STUDENT 
);
```

### Write an SQL query to show one row twice in results from a table.

```SQL
SELECT *FROM student
UNION ALL
SELECT *FROM STUDENT ORDER BY STUDENT_ID;
```

### Write an SQL query to list STUDENT_ID who does not get Scholarship.
```SQL
SELECT *FROM student S
LEFT JOIN SCHOLARSHIP SH ON S.STUDENT_ID=SH.STUDENT_REF_ID
WHERE SH.STUDENT_REF_ID IS NULL;
```

or

```sql
SELECT *FROM student
WHERE STUDENT_ID NOT IN ( SELECT STUDENT_REF_ID FROM SCHOLARSHIP);
```

### Write an SQL query to fetch the MAJOR subject that have less than 4 people in it.
```sql
SELECT MAJOR,COUNT(*) FROM STUDENT
GROUP BY MAJOR
HAVING COUNT(*)<4;
```

### Write an SQL query to show the last record from a table.
```sql
SELECT *FROM student
ORDER BY STUDENT_ID DESC
LIMIT 1;
```

### Write an SQL query to show the first record from a table.
```sql
SELECT *FROM student
ORDER BY STUDENT_ID ASC
LIMIT 1;
```
### Write an SQL query to fetch the last five records from a table.
```sql
SELECT * FROM (
SELECT *FROM student
ORDER BY STUDENT_ID DESC
LIMIT 5) AS order_list
ORDER BY STUDENT_ID ASC;
```

### Write an SQL query to fetch three max GPA from a table
```sql
-- COMMON TABLE EXPRESSION(USED TO AVOID ->  This version of MySQL doesn't yet support 'LIMIT & IN/ALL/ANY/SOME subquery')
WITH TOP_3 AS(
SELECT DISTINCT GPA FROM student
ORDER BY GPA ASC
LIMIT 3
)
SELECT *FROM student
WHERE GPA IN (SELECT GPA FROM TOP_3);
```
### Write an SQL query to fetch MAJOR subjects along with the max GPA in each of these MAJOR subjects.

```SQL
SELECT MAJOR,MAX(GPA) FROM student
GROUP BY MAJOR;
```

###  Write an SQL query to fetch the names of Students who has highest GPA.

```SQL
SELECT FIRST_NAME,GPA FROM STUDENT
ORDER BY GPA DESC
LIMIT 1;
```

### CURRENT

```SQL
SELECT CURRENT_DATE(); -- 2025-05-15
SELECT current_time(); -- 19:33:49
SELECT current_timestamp(); -- 2025-05-15 19:33:59 
 SELECT NOW();-- 2025-05-15 19:33:59 
SELECT current_user(); -- root@localhost
```

### Write a query to create a new table which consists of data and structure copied from the other table (say Student) or clone the table named Student.
```SQL
CREATE TABLE CLONETABLE AS SELECT *FROM STUDENT;
```

###  Write an SQL query to update the GPA of all the students in 'Computer Science' MAJOR subject to 7.5.

```sql
UPDATE STUDENT 
SET GPA=7.5
WHERE MAJOR='Computer Science';
```

### Write an SQL query to find the average GPA for each major.
```sql
SELECT AVG(GPA) FROM STUDENT
GROUP BY MAJOR;
```
### Write an SQL query to find the number of students in each major who have a GPA greater than 7.5.

```sql
SELECT MAJOR,COUNT(STUDENT_ID) FROM STUDENT
WHERE GPA>7.5
GROUP BY MAJOR
```

###  Write an SQL query to find the students who have the same GPA as 'Shivansh Mahajan.
```SQL
SELECT *FROM student
WHERE GPA=(
SELECT GPA FROM STUDENT 
WHERE STUDENT_ID=201);
```










