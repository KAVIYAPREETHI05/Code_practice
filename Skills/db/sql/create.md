### 1.Write a MySQL query to create a simple table countries including columns country_id, country_name and region_id.

```sql
CREATE TABLE countries(
COUNTRY_ID varchar(2),
COUNTRY_NAME varchar(50),
REGION_ID decimal(10,0)
);
```
### 2. Write a MySQL query to create a simple table countries including columns country_id, country_name and region_id which is already exists.

```sql
CREATE TABLE IF NOT EXISTS countries(
COUNTRY_ID varchar(2),
COUNTRY_NAME varchar(50),
REGION_ID decimal(10,0),
REGION_NAME  varchar(50)
);
```
### 3. Write a MySQL query to create the structure of a table dup_countries similar to countries.

```sql
CREATE TABLE IF NOT EXISTS newTable (
  COUNTRY_ID varchar(2),
  COUNTRY_NAME varchar(50),
  REGION_ID decimal(10,0),
  REGION_NAME varchar(50)
);

```
(or)
```sql
CREATE TABLE IF NOT EXISTS flower LIKE countries;
```
