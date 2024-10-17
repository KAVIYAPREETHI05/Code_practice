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

``sql
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
### DROP 

Used to delete database objects like tables, views, indexes, or the database itself.

```sql
DROP TABLE Employees;  -- Deletes the Employees table
DROP DATABASE CompanyDB;  -- Deletes the entire database

```

### TRUNCATE

Used to remove all records from a table but keep the table structure intact. It is faster than DELETE since it does not log individual row deletions.

```sql
TRUNCATE TABLE Employees;  -- Removes all data from Employees table

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
### COMMENT

 Adds or modifies comments on a table, column, or other objects.

 ```sql
COMMENT ON TABLE Employees IS 'Stores employee details';
COMMENT ON COLUMN Employees.Age IS 'Age of the employee';
```
