## JOINS

## INNER JOIN

### Get employee names along with their department names.
![image](https://github.com/user-attachments/assets/99a50d8a-8796-4964-b140-66e1fc3f8d9a)
![image](https://github.com/user-attachments/assets/1970566b-c661-44d4-936e-7cb3fdd3d8bf)

```sql
SELECT EmpName,DeptName FROM Empolyees
INNER JOIN Departments
ON Empolyees.DeptID=Departments.DeptID;
```
![image](https://github.com/user-attachments/assets/20bdc0d2-8e95-4733-aed0-87c8210eb587)

## LEFT JOIN

```sql
SELECT EmpName,DeptName FROM Empolyees
LEFT JOIN Departments
ON Empolyees.DeptID=Departments.DeptID;
```
![image](https://github.com/user-attachments/assets/486573b7-488e-43d8-8dfc-7501b9622f1a)


 ## RIGHT JOIN

 ```sql
SELECT EmpName,DeptName FROM Empolyees
RIGHT JOIN Departments
ON Empolyees.DeptID=Departments.DeptID;
```
![image](https://github.com/user-attachments/assets/36a85276-abb2-4308-83ff-87207e20d06a)

## FULL JOIN

```SQL

SELECT EmpID,EmpName,DeptName
FROM empolyees
LEFT JOIN departments
ON empolyees.DeptID=departments.DeptID
UNION
SELECT EmpID,EmpName,DeptName
FROM empolyees
RIGHT JOIN departments
ON empolyees.DeptID=departments.DeptID;
```

![image](https://github.com/user-attachments/assets/13dc5a19-0be4-49e0-902f-dedf272c137b)

###  Find all employees who work in the 'IT' department.

```sql
SELECT EmpName
FROM Empolyees
INNER JOIN Departments
ON Empolyees.DeptID=Departments.DeptID
WHERE DeptName='IT';
```

![image](https://github.com/user-attachments/assets/57d6ef27-26bb-4da0-a2dd-d28b7a9799d7)

###  List department names and the number of employees in each department.

```sql
SELECT DeptName,COUNT(EmpID) AS NumEmpolyees
FROM Empolyees
INNER JOIN Departments
ON Empolyees.DeptID=Departments.DeptID
GROUP BY DeptName;
```

![image](https://github.com/user-attachments/assets/4b2b291a-c1b7-415c-84f3-00929e53c801)

### Display employees whose salary is more than 60000 and also show their department.

```sql
SELECT EmpName,DeptName,salary
FROM empolyees
INNER JOIN Departments
ON empolyees.DeptID=Departments.DeptID
WHERE salary>60000;
```

![image](https://github.com/user-attachments/assets/2ce827bc-7e16-4273-b065-c9db717b4d19)

### Find the average salary in each department.
```sql
SELECT DeptName,AVG(salary) AS avgSalary
FROM empolyees
INNER JOIN Departments
ON empolyees.DeptID=Departments.DeptID
GROUP BY DeptName;
```
![image](https://github.com/user-attachments/assets/c982535c-dfc9-4c32-b178-c45f62061395)

### Get a list of all students along with their subjects and marks.
(Show students even if they have no marks.)

```SQL
SELECT Students.name, Marks.subject, Marks.marks
FROM Students
LEFT JOIN Marks
ON Students.student_id = Marks.student_id;
```
### List all students and their attendance details.
(Show students even if their attendance is missing.)

```SQL
SELECT Students.name, Attendance.total_days, Attendance.present_days
FROM Students
LEFT JOIN Attendance
ON Students.student_id = Attendance.student_id;
```

### Get a list of students who have both marks and attendance records.
(Only students present in both.)
```SQL
SELECT Students.name
FROM Students
INNER JOIN Marks
ON Students.student_id = Marks.student_id
INNER JOIN Attendance
ON Students.student_id = Attendance.student_id;

```

### Find students who have attendance but are not present in the Students table
```SQL
SELECT Attendance.student_id, Attendance.total_days, Attendance.present_days
FROM Attendance
LEFT JOIN Students
ON Attendance.student_id = Students.student_id
WHERE Students.student_id IS NULL;
```

### Get all students' names, marks, and attendance details together (even if some parts are missing).
```SQL

SELECT S.name,M.MARKS,A.PRESENT_DAYS FROM STUDENTS S
LEFT JOIN MARKS M ON S.STUDENT_ID=M.STUDENT_ID
LEFT JOIN ATTEND A ON S.STUDENT_ID=A.STUDENT_ID;
```

### Write a query to find the names of employees who have made at least one order.

```sql
SELECT E.NAME FROM EMPLOYEES E
JOIN ORDERS O ON E.EMPLOYEE_ID=O.EMPLOYEE_ID;
```


### Write a query to find the names of employees who have made no one order.
```sql
SELECT E.NAME FROM EMPLOYEES E
LEFT JOIN ORDERS O ON E.EMPLOYEE_ID=O.EMPLOYEE_ID
WHERE O.EMPLOYEE_ID IS NULL;
```
### Write a query to find the total sales (Order_Value) handled by each employee. Display the Employee_ID, Name, and the total sales value, ordered by total sales in descending order.

```sql
SELECT E.EMPLOYEE_ID,E.NAME,SUM(O.ORDER_VALUE) AS TOTAL_SALE FROM EMPLOYEES E
LEFT JOIN ORDERS O ON E.EMPLOYEE_ID= O.EMPLOYEE_ID
GROUP BY E.EMPLOYEE_ID,E.NAME
ORDER BY TOTAL_SALE DESC;
```

### Query to display the total sales (Order_Value) for each employee's department.
```
sql
SELECT E.Employee_ID, E.Name, E.Department, SUM(O.Order_Value) AS Total_Sales
FROM Employees E
LEFT JOIN Orders O ON E.Employee_ID = O.Employee_ID
GROUP BY E.Employee_ID, E.Name, E.Department;

```
## Leetcode

### Write a solution to report all the duplicate emails. Note that it's guaranteed that the email field is not NULL.

```sql
SELECT Email FROM PERSON
GROUP BY EMAIL
HAVING COUNT(EMAIL)>1
```

![image](https://github.com/user-attachments/assets/c86508a1-dc98-4fad-b9ba-549de4a7355f)

```sql
SELECT E.NAME AS Employee FROM EMPLOYEE E
JOIN EMPLOYEE M ON E.MANAGERID=M.ID
WHERE E.SALARY >M.SALARY;
```

### Write a solution to report the first name, last name, city, and state of each person in the Person table. If the address of a personId is not present in the Address table, report null instead.

```sql
SELECT P.FIRSTNAME,P.LASTNAME,A.CITY,A.STATE FROM PERSON P
LEFT JOIN ADDRESS A ON P.PERSONID=A.PERSONID;
```

### Write a solution to find the second highest distinct salary from the Employee table. If there is no second highest salary, return null 
```SQL
SELECT (SELECT DISTINCT SALARY  FROM EMPLOYEE
ORDER BY SALARY DESC
LIMIT 1 OFFSET 1) AS SECONDHIGHESTSALARY;
```

### over()
The OVER() clause is used with window functions in SQL to define a window of rows that the function operates on. It allows you to perform calculations across a set of table rows that are somehow related to the current row.
OVER() works with various window functions like ROW_NUMBER(), RANK(), DENSE_RANK(), and SUM(). 

```sql
SELECT SCORE, DENSE_RANK() OVER(ORDER BY SCORE DESC)  AS 'rank' FROM SCORES;

```

### IE
Takes employee salary and joining date (in DD-MM-YYYY format),

Checks which day of the week it is,

Adds extra salary based on the weekday:

Monday → +100

Wednesday → +200

Sunday → +120

Other days → +80
```SQL
SELECT 
    employee_id,
    employee_name,
    salary,
    entry_date,
    CASE 
        WHEN TO_CHAR(TO_DATE(entry_date, 'DD-MM-YYYY'), 'DAY') LIKE 'MON%' THEN salary + 100
        WHEN TO_CHAR(TO_DATE(entry_date, 'DD-MM-YYYY'), 'DAY') LIKE 'WED%' THEN salary + 200
        WHEN TO_CHAR(TO_DATE(entry_date, 'DD-MM-YYYY'), 'DAY') LIKE 'SUN%' THEN salary + 120
        ELSE salary + 80
    END AS updated_salary
FROM 
    employee_table;
```


