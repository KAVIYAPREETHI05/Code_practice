## TCL - Transaction Control Language

A single unit of work in a database is formed after the consecutive execution of commands is known as a transaction.


**COMMIT**
Purpose: Saves all changes made in the current transaction permanently to the database.

Irreversible: Once committed, you cannot roll back.

**ROLLBACK**
Purpose: Undoes all changes made since the last COMMIT.

Reverts the database to the last committed state.

**SAVEPOINT**
Purpose: Creates a named point within a transaction to which you can roll back partially.

Used with ROLLBACK TO SAVEPOINT.

**START TRANSACTION**
It turns off auto-commit temporarily.

All following SQL statements become part of a single transaction until you issue COMMIT or ROLLBACK.


```sql
SET autocommit = 0; //disable auto commit
```

### COMMIT

```SQL
START TRANSACTION;

UPDATE BANK
SET balance= balance+4000 
WHERE account_no=101;

UPDATE Bank
SET balance=balance-4000
WHERE account_no=102;

SELECT *FROM Bank;
COMMIT; //saves permanetly cannot be roll back
ROLLBACK; //error

```


### ROLLBACK

```SQL
START TRANSACTION;

UPDATE BANK
SET balance= balance+4000 
WHERE account_no=101;

UPDATE Bank
SET balance=balance-4000
WHERE account_no=102;

SELECT *FROM Bank; //8000 0
ROLLBACK;
SELECT*FROM Bank; //4000 4000

```

### SAVEPOINT

```sql

SET AUTOCOMMIT=0;
INSERT INTO Bank (account_no, holder_name, balance) VALUES
(105, 'Aliya', 5000.00);
SAVEPOINT sp1;

INSERT INTO Bank (account_no, holder_name, balance) VALUES
(106, 'Iliya', 10000.00);

SELECT *FROM Bank;  // 101 102 103 104 105 106

ROLLBACK TO sp1;
SELECT *FROM Bank;  //101 102 103 104 105

```

### check whether autocommit is on or off

```sql

SELECT @@autocommit;
```

### Transfer ₹2000 from Alice to Bob and Charlie. If Charlie's credit fails, rollback only that part — but keep Bob's transfer.

```sql
CREATE TABLE Bank(
account_id INT PRIMARY KEY,
holder_name VARCHAR(50),
balance INT);

INSERT INTO Bank(account_id,holder_name,balance)
VALUES(101,'Alice',3000),
(102,'Bob',1000),
(103,'Charles',5000);

UPDATE Bank
SET balance =balance-2000
WHERE account_id=101;  //1000 1000 5000
SAVEPOINT after_deduction;

UPDATE Bank 
SET balance=balance+1000
WHERE account_id=102; // 1000 2000 5000
SAVEPOINT bob;

UPDATE Bank
SET balance=balance+1000
WHERE account_id=103; // 1000 2000 6000
SAVEPOINT charles;

SELECT *FROM Bank;
ROLLBACK TO bob;

SELECT *FROM Bank; //1000 2000 5000


```

