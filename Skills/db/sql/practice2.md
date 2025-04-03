## HACKER RANK

### Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION
WHERE CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%';

```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[AEIOU]';

### Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION
WHERE CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE'%O' OR CITY LIKE '%U';
```

### Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION
WHERE( CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE'%O' OR CITY LIKE '%U')
AND
( CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE'O%' OR CITY LIKE 'U%');
```

### Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION
WHERE CITY  NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND NOT CITY LIKE 'O%' AND CITY NOT LIKE 'U%';
```
### Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION
WHERE( CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE'%O' AND CITY NOT LIKE '%U');
```

### Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

```sql
SELECT DISTINCT CITY FROM STATION
WHERE( CITY NOT LIKE '%A' AND CITY NOT LIKE '%E' AND CITY NOT LIKE '%I' AND CITY NOT LIKE'%O' AND CITY NOT LIKE '%U')
OR
( CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%' AND CITY NOT LIKE 'I%' AND CITY NOT LIKE'O%' AND CITY NOT LIKE 'U%');
```

```sql
SELECT DISTINCT CITY FROM STATION
WHERE CITY NOT REGEXP '^[AEIOU]' 
AND CITY NOT REGEXP '[AEIOU]$';
```
