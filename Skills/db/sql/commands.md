## SQL COMMANDS

# DATABASE

- **create**

```slq
CREATE DATABASE db1;
```
- **drop**

```sql
DROP DATABASE db1;
```

- **rename**

```sql
RENAME DATABASE old_name TO new_name
```
```sql

ALTER DATABASE old
MODIFY NAME=new;
```

- **select**

```sql
USE db1;
```

# TABLE 

- **CREATE**

```sql
 CREATE TABLE exam(sub_id INT PRIMARY KEY, 
 course VARCHAR(50),
 dept VARCHAR(50),
 exam_date DATE,
 marks INT,
 result BOOLEAN);
```
![image](https://github.com/user-attachments/assets/310c9f53-2e6e-4f39-82b3-d3ddbabc1fbd)

creating table form another table with data

```sql
// copy in sql( SELECT *INTO new_table FROM old_table)
CREATE TABLE similar AS
SELECT *FROM exam;
```
![image](https://github.com/user-attachments/assets/a421293f-1fa6-476c-af00-abd9a12bbee5)


creating table from another table  without data

```sql
CREATE TABLE struct_similar AS
SELECT *FROM similar WHERE 1=0;
```

![image](https://github.com/user-attachments/assets/446f6439-2f83-498d-869c-30a4fa58152b)

- **DROP**  - Removes the entire table/database

```sql
DROP TABLE student
```
- **DELETE**  - Removes specific rows

```sql
DELETE FROM similar WHERE course='aws'
```

![image](https://github.com/user-attachments/assets/26c91787-86d8-4705-b1be-bc6b74c8669d)

```sql
// removes all rows but does not free space containing by table 
DELETE FROM similar
 ```

![image](https://github.com/user-attachments/assets/956819f9-4273-4e1a-9fc2-242b5b85629b)


- **TRUNCATE** - Removes all rows

```sql
TRUNCATE TABLE struct_similar
```

![image](https://github.com/user-attachments/assets/9314d4fc-f944-4cf4-bae4-5bf680a4c8bb)


 - **RENAME**

```sql
ALTER TABLE similar
RENAME  TO disimilar;
```

**TEMP TABLES**

 -  - Local temp variables -Local temp tables are only available at current connection time. It is automatically deleted when user disconnects from instances. It is started with hash (#) sign.
    - Global temp variables -Global temp tables name starts with double hash (##). Once this table is created, it is like a permanent table. It is always ready for all users and not deleted until the total connection is withdrawn.
  
**local temp table**
sql
```sql
CREATE TABLE #local temp table (  
    User id int,  
    Username varchar(50),  
    User address varchar(150)  
);

```
mysql
```sql
CREATE TEMPORARY TABLE temp_table(
  id INT,
  age INT)
```

**gloal temp table**

sql

```sql
CREATE TABLE ##new global temp table (  
User id int,  
User name varchar (50),  
User address varchar (150)  
)
```


MySQL doesn’t have true global temporary tables.

- **ALTER**



























### SELECT

```sql
 SELECT *FROM  practice;
```
![image](https://github.com/user-attachments/assets/f6d64dbb-427c-4cd3-b96d-047ff80bcd0b)

### INSERT

```sql
INSERT INTO exam(sub_id,course,dept,exam_date,marks,result)
 VALUES (02,"aws","it",'2026-03-12',90,true),
 (03,"dsa","ise",'2002-09-24',20,FALSE),
 (04,"math","ise",'2002-03-24',20,FALSE),
 (05,"science","mec",'2003-09-24',20,TRUE),
 (06,"pthysics","ml",'2023-09-24',20,FALSE);

```

![image](https://github.com/user-attachments/assets/eb874bd7-3ef5-463a-ba2f-72cd86959fcd)




