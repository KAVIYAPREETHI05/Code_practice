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

