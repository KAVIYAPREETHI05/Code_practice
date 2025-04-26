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

```
Here are some unique and diverse SQL query practice questions for you:

1. Retrieve the names of employees who have worked more than 100 hours in total in a given month.
2. Find the top 3 highest paid employees in each department.
3. List all products that are not sold in any order.
4. Display the average salary of employees who have been with the company for more than 5 years.
5. Find customers who have purchased all products in a particular category.
6. Retrieve the names of students who have completed more than 3 courses but haven't attended any exams.
7. Get the employees who have not been assigned to any projects.
8. Find the product(s) with the highest quantity sold in a given year.
9. Display the total number of orders placed by each customer in the past month.
10. Get all employees who have joined the company in the last 6 months and have not received a promotion.
11. Retrieve the list of books that have been checked out more than 5 times.
12. Find the difference in the number of orders between two given months for each product.
13. Get the employees who have worked on exactly one project.
14. List the employees who have reported more than 2 absences this year but have a salary greater than $50,000.
15. Find customers who have purchased products from every available category.
16. Retrieve the names of suppliers who have supplied products that have never been sold.
17. Get the average order value for each customer in the last 6 months.
18. List the employees who have completed training but have not yet been assigned a task.
19. Retrieve the names of all customers who have purchased a product that is currently out of stock.
20. Find the employees who have worked on projects that are still active but have not received any feedback.

```

