## Data Definition Language

- CREATE: Defines new database objects.
- ALTER: Modifies existing database objects.
- DROP: Deletes database objects.
- TRUNCATE: Removes all records from a table while keeping the structure.
- RENAME: Changes the name of database objects.
- COMMENT: Adds comments to describe objects.

### CREATE

Used to create database objects like tables, views, indexes, etc.

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Age INT,
    HireDate DATE
    salary DECIMAL(10,2); -- DECIMAL (Fixed-Point Precision)
    price DOUBLE; -- (Floating-Point Precision)
);

```
### ALTER

Used to modify the structure of an existing database object (e.g., adding or dropping columns, renaming tables).

```sql
ALTER TABLE Employees
ADD Email VARCHAR(100);
```

```sql
ALTER TABLE Employees
DROP COLUMN Email;
```

```sql
ALTER TABLE Customers
RENAME COLUMN 'phone' TO 'phoneNumber';
```

```sql
ALTER TABLE Customers
MODIFY phoneNumber VARCHAR(15);
```

```sql
ALTER TABLE Customers
DROP COLUMN phoneNumber;
```

```sql
ALTER TABLE Customers
ADD CONSTRAINT age PRIMARY KEY(int);
```

```sql
ALTER TABLE orders
DROP PRIMARY KEY;
```

```sql
ALTER TABLE orders
ADD CONSTRAINT fk_customer_id FOREIGN KEY (customer_id) REFERENCES customers(id);
```

```sql
ALTER TABLE orders
DROP FOREIGN KEY fk_customer_id;
```

```sql
ALTER TABLE Customers
CHANGE age customerAge int;
```

```sql
ALTER TABLE Customers
ADD CONSTRAINT unique_key UNIQUE(age);
```

```sql
ALTER TABLE Customers
DROP  INDEX unique_key
```
```sql
ALTER TABLE users
ALTER COLUMN status SET DEFAULT 'active';
```

```sql
ALTER TABLE Customers 
RENAME TO Students;
```
```sql
ALTER TABLE Students
MODIFY customer_id INT AUTO_INCREMENT;
```

```sql
ALTER TABLE Students
MODIFY customer_id INT AFTER first_name;

```
```sql
ALTER TABLE Students
MODIFY customer_id VARCHAR(100);

```

```sql
ALTER TABLE users
ADD CONSTRAINT chk_age CHECK (age >= 18);

```
### DROP 

Used to delete database objects like tables, views, indexes, or the database itself.

```sql
DROP TABLE Employees;  -- Deletes the Employees table
DROP DATABASE CompanyDB;  -- Deletes the entire database

```
```sql
ALTER TABLE Shippings -- drop column
DROP COLUMN status;
```
```sql
DROP INDEX idx_name;
```
```sql
DROP VIEW employee_view;
```
```sql
ALTER TABLE Shippings
DROP FOREIGN KEY fk_key;
```
```sql
ALTER TABLE Shippings
DROP PRIMARY KEY;
```
```sql
ALTER TABLE Shippings
DROP CONSTRAINT uni_key;
```
```sql
DROP TEMPORARY TABLE temp_sales_data;

```
```sql
DROP TRIGGER update_salary; -- automatic updates on a table
DROP PROCEDURE calculate_salary;
DROP FUNCTION get_employee_salary;
DROP TEMPORARY TABLE temp_sales_data;
DROP EVENT daily_backup;
DROP SEQUENCE order_seq;
DROP USER db_user;

```
```sql
ALTER TABLE Shippings
MODIFY customer INT;  -- remove auto increment

```
```sql
ALTER TABLE employees ALTER COLUMN status DROP DEFAULT;

```

### TRUNCATE

Used to remove all records from a table but keep the table structure intact. It is faster than DELETE since it does not log individual row deletions.

```sql
TRUNCATE TABLE Employees;  -- Removes all data from Employees table
TRUNCATE TABLE orders CASCADE;
TRUNCATE TABLE sales PARTITION (p1);
TRUNCATE TABLE orders, products;
TRUNCATE TABLE sales_db.orders; -- specific db


```

### RENAME

 Used to rename database objects such as tables or columns.

```sql
ALTER TABLE Employees RENAME TO Students; --tablename
```
```sql
alter table Students 
rename FirstName to Name;
```
```sql
SELECT first_name AS first, last_name AS last
FROM Customers;
```
```sql
SELECT CONCAT(first_name, ' ', last_name) AS FullName
FROM Customers;
```
```sql
SELECT COUNT(*) AS ordercount
FROM Orders;
```
```sql
SELECT SUM(amount) AS ordercount
FROM Orders;
```
```sql
SELECT amount * 0.1 AS yearlybonus
FROM Orders;
```
```sql
SELECT e.item
FROM Orders AS e;
```
```sql
SELECT MAX(amount)  AS maxAmount
FROM orders;
```
```sql
SELECT FirstName, LastName
FROM Employees
UNION
SELECT FirstName, LastName
FROM Contractors;
```
```sql
SELECT AVG(amount) AS ordercount
FROM Orders;
```
### COMMENT

 Adds or modifies comments on a table, column, or other objects.

 ```sql
COMMENT ON TABLE Employees IS 'Stores employee details';
COMMENT ON COLUMN Employees.Age IS 'Age of the employee';
```
