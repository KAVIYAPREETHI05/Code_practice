### Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

```SQL
SELECT NAME FROM EMPLOYEE
ORDER BY NAME ASC;
```

### Query the Name of any student in STUDENTS who scored higher than  Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

```sql
SELECT Name FROM STUDENTS
WHERE MARKS>75
ORDER BY RIGHT(Name,3) ASC, ID ASC;
```

### Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than  per month who have been employees for less than  months. Sort your result by ascending employee_id.

```SQL
SELECT NAME FROM EMPLOYEE
WHERE SALARY >2000 AND MONTHS<10
ORDER BY EMPLOYEE_ID ASC;
```

## JOIN

### Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

```sql
SELECT SUM(CITY.POPULATION) FROM CITY
LEFT JOIN COUNTRY ON CITY.COUNTRYCODE=COUNTRY.CODE
WHERE COUNTRY.CONTINENT='Asia';
```

### Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

```sql
SELECT CITY.NAME FROM CITY
LEFT JOIN COUNTRY ON CITY.COUNTRYCODE=COUNTRY.CODE
WHERE COUNTRY.CONTINENT='Africa';

```

## CODECHEF

### Write a query to output all the columns from the Products table.

```sql
SELECT *FROM PRODUCTS
```


### Write a query to find all product_name and category that have a price greater than 100.00 from the Products table.

```sql
select PRODUCT_NAME,CATEGORY FROM PRODUCTS
WHERE PRICE>100.00
```

### Write a query to calculate the average salary across all companies combined. Rename the column as avg_salary. 
```sql
SELECT AVG(SALARY) AS AVG_SALARY FROM WORKS;
```

### Write a query to retrieve the department_name and location of people who live in location that starts with 'S'. 

```sql
SELECT DEPARTMENT_NAME,LOCATION from departments 
WHERE LOCATION LIKE 's%';
```

### Write a query to select all the distinct companies (company_name) in the Works table.

```sql
SELECT DISTINCT COMPANY_NAME FROM WORKS;
```
### Write a query to find the total count of books whose genre is Fiction.
Note: Output column name should be fiction_count.
```sql
SELECT COUNT(ID) AS fiction_count FROM BOOKS
WHERE GENRE = 'Fiction';
```

### Write a query to select only the movie names where the ratings are greater than 7 but less than 9.

```sql
SELECT MOVIE_NAME FROM CINEMA 
WHERE RATING>7 AND RATING<9;
```
### Write a query to retrieve book_id, title, author and published_year of the books which have NULL rating for their books. 

```sql
SELECT book_id,title,author,published_year FROM LIBRARY
WHERE RATING IS NULL;
```

### Create a query to retrieve the employee_name, company, and salary for employees in the full-time category, ordered by salary in descending order 
```sql
SELECT employee_name,company,salary FROM EMPLOYEES
WHERE CATEGORY='Full-Time'
ORDER BY  SALARY DESC;
```

### Write a query to group the employees by their department and display the total number of employees (as total_employees) in each department. 
```SQL
SELECT DEPARTMENT, COUNT(*) AS TOTAL_EMPLOYEES FROM EMPLOYEES
GROUP BY DEPARTMENT;

```

### Write a query to retrieve the author_id, author_name, and publication_name for authors whose articles got zero views. The result should be sorted by author_id in ascending order. 
```sql
SELECT AUTHOR_ID,AUTHOR_NAME,PUBLICATION_NAME FROM VIEWS
WHERE VIEW_COUNT=0
ORDER BY AUTHOR_ID ASC;
```

### Write a query to find the names of the top 3 distinct players by highest score who have won matches, including their scores.
```sql
SELECT DISTINCT p.player_name, p.score
FROM players p
JOIN matches m ON m.winner = p.player_name
ORDER BY p.score DESC
LIMIT 3;
```



