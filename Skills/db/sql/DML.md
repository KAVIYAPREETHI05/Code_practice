## Data Manipulation Language

- INSERT: Adds new data to the table.
- UPDATE: Modifies existing data in the table.
- DELETE: Removes data from the table.
- SELECT: Retrieves data from the table (though it's not technically "manipulating" data).

### INSERT

Used to add new rows of data to a table.

```sql
INSERT INTO Employees (EmployeeID, FirstName, LastName, Age, HireDate)
VALUES (1, 'John', 'Doe', 30, '2023-01-15');
```
### UPDATE

Used to modify existing data in a table.

```sql
UPDATE Employees
SET Age = 31
WHERE EmployeeID = 1;

```
### DELETE

Used to remove rows from a table.

```sql
DELETE FROM Employees
WHERE EmployeeID = 1;

```

### SELECT

 Used to query and retrieve data from the database (not modifying but retrieving data).

 ```sql
SELECT FirstName, LastName, Age
FROM Employees
WHERE Age > 25;
```
```sql
SELECT *FROM Employees;
```

### MERGE

 Used to perform an INSERT, UPDATE, or DELETE operation in a single command (supported in some databases like SQL Server and Oracle).

 ```sql
MERGE INTO Employees AS target
USING NewEmployees AS source
ON target.EmployeeID = source.EmployeeID
WHEN MATCHED THEN
    UPDATE SET target.Age = source.Age
WHEN NOT MATCHED THEN
    INSERT (EmployeeID, FirstName, LastName, Age)
    VALUES (source.EmployeeID, source.FirstName, source.LastName, source.Age);

```
