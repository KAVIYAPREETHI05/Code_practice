## DATATYPES
### create table
```sql
create table students(
  id int,
  age integer,
  fees decimal(10,2),/* 10digits 2 digit after dot *//*accurate*/
  measurement float, /* approximate*/
  weight double,
  class char(5),/* fixed length */
  name varchar(20),/*variable length*/
  description text,/*large text area*/
  birthdate date,/* YYYY-MM-DD format*/
  adtime time, /*HH:MM:SS format*/
  eventTime datetime, /*YYYY-MM-DD HH:MM:SS format*/
  isactive boolean
  );
```
### insert values
```sql
insert into students(id,age,fees,measurement,weight,class,name,description,birthdate,adtime,eventTime,isactive)
values(2,22,20000,23.34,2323.43,'V','kavi','she is very good girl','2005-02-19','23:23:23','2005-02-19 23:23:23',true);
```

