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


