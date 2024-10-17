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

```sql
INSERT INTO Shippings(shipping_id,customer)
VALUES (6,5);
```
```sql
INSERT INTO Orders(item,customer_id)
VALUES ('Keychain',5);  -- Insert with Specific Columns
```
```sql
INSERT INTO Orders(item,customer_id)
VALUES ('Keychain',3),('marker',4);  -- multiple values
```
```sql
INSERT INTO Orders(amount)
SELECT MAX(customer)
FROM Shippings;
```
```sql
INSERT INTO ActiveCustomers (CustomerID, CustomerName)
SELECT CustomerID, CustomerName
FROM Customers
WHERE IsActive = 1;
```
```sql
INSERT INTO Orders (OrderID, CustomerID, OrderDate)
VALUES (3, 3, CURDATE());

```
### UPDATE

Used to modify existing data in a table.

```sql
UPDATE Employees
SET Age = 31
WHERE EmployeeID = 1;

```
```sql
UPDATE Orders
SET item='color',amount=90000
WHERE order_id=7;
```
```sql
UPDATE Orders
SET status = 'delivered'
WHERE order_id IN (1001, 1002, 1003);
```
```sql

UPDATE Orders
SET amount=amount*0.1;
```
```sql
UPDATE Users
SET status = 'inactive'
WHERE last_login < DATE_SUB(NOW(), INTERVAL 1 YEAR);

```
```sql
UPDATE Orders
SET item='hello'
WHERE item LIKE 'key%';
```
```sql
UPDATE Employees
SET email = REPLACE(email, 'oldcompany.com', 'example.com')
WHERE email LIKE '%oldcompany.com%';
```
```sql
UPDATE Orders
SET amount=CASE
WHEN item='hello'
THEN 1000
ELSE 5000
END;
```
```sql
UPDATE Customers
SET phone_number = 'Unknown'
WHERE phone_number IS NULL;

```
```sql
UPDATE Products
SET stock = stock + 10
LIMIT 5;
```
### DELETE

Used to remove rows from a table.
```sql
DELETE FROM Orders;
```
```sql
DELETE FROM Employees
WHERE EmployeeID = 1;

```
```sql
DELETE FROM Orders
WHERE item='hello';
```
```sql
DELETE FROM Orders
WHERE item LIKE 'M%';
```
```sql
DELETE FROM Orders
WHERE item IS NULL;
```
```sql
DELETE FROM Orders
WHERE order_id IN (101, 102, 103);
```
```sql
DELETE FROM Orders
WHERE customer_id IN (SELECT customer_id FROM Customers WHERE city = 'New York');
```
```sql
DELETE FROM Logs
WHERE log_date < DATE_SUB(NOW(), INTERVAL 6 MONTH);
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
