## WEEK-1

### 1. Write a Java program to print the area and perimeter of a rectangle.
```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        double width;
        double height;
        
        Scanner scan =new Scanner(System.in);
        width=scan.nextDouble();
        height=scan.nextDouble();
        
        double perimeter=2*(height+width);
        double area=height*width;
        
        System.out.printf("Perimeter is 2*(%.1f + %.1f) = %.1f\n",height,width,perimeter);
        System.out.printf("Area is %.1f * %.1f = %.1f",width,height,area);
    }
}
```

### 2.Write a Java program and compute the sum of an integer's digits.

```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        Scanner scan =new Scanner(System.in);
       long number=scan.nextLong();
        int sum=0;
       while(number!=0){
           sum+=number%10;
           number/=10;
       }
       
        System.out.print("The sum of the digits is: " + sum);
}
}
```
### 3.Write a Java program to display n terms of natural numbers and their sum.
```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        Scanner scan =new Scanner(System.in);
       int number=scan.nextInt();
        int sum=0;
       for(int i=1;i<=number;i++){
           System.out.println(i);
           sum+=i;
       }
       
        System.out.print("The Sum of Natural Number upto "+number+"terms :"+ sum);
}
}
```

### 4.Write a Java program to make such a pattern like a right angle triangle with the number increased by 1.
```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        Scanner scan =new Scanner(System.in);
       int number=scan.nextInt();
        int k=1;
       for(int i=1;i<=number;i++){
           for(int j=1;j<=i;j++){
               System.out.print(k+++" ");
               
           }
           System.out.println("\n");
       }
       
       
}
}
```

### 5.Write a Java program to convert an integer number to a binary number.
```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        Scanner scan =new Scanner(System.in);
       int number=scan.nextInt();
       int quot=number;
          int i=1;
        int bin_num[]=new int[100];
        while(quot!=0){
            bin_num[i++]=quot%2;
            quot/=2;
            
        }
      
        
        System.out.print("Binary number is: ");
        for(int j=i-1;j>0;j--){
            System.out.print(bin_num[j]);
        }
       
       
}
}
```
## WEEK-2

### 1.Complete the code segment to call the method  display() of class Former first and then call display() method of class Latter.
```java
import java.util.*;

class Former{
    public void display(){
        System.out.println("This is Former Class.");
    }
}

class Latter{
    public void display(){
        System.out.println("This is Latter Class.");
    }
}

class Main {
    
    public static void main(String[] args) {
        
       Former f=new Former();
       f.display();
       Latter l=new Latter();
       l.display();
}
}
```

### 2.Create a class Student with private attributes for name and age.
```java
import java.util.*;

class Student{
    private String name;
    private int age;
    
    Student(String name,int age){
        this.name=name;
        this.age=age;
    }
    public String getName(){
        return name;
    }
    public int getAge(){
        return age;
    }
}


class Main {
    
    public static void main(String[] args) {
        
      Student std=new Student("Kaviya",23);
      
      System.out.println("Student Name: "+std.getName());
      System.out.println("Student Age: "+std.getAge());

}
}
```

### 3.Create a class Rectangle with attributes length and width.


```java
import java.util.*;

class Rectangle{
    private double length;
    private double width;
    
    public Rectangle(){
        this.length=1;
        this.width=1;
    }
    
    Rectangle(double length,double width){
        this.length=length;
        this.width=width;
    }
    
    public double getLength(){
        return length;
    }
    public double getWidth(){
        return width;
    }
    public double getArea(){
        return length*width;
    }
}
class Main {
     public static void main(String[] args) {
      Rectangle r=new Rectangle();
      Rectangle r2=new Rectangle(2,3);
      
      System.out.println("Default Rectangle: "+r.getArea());
      System.out.println("Parameterised Reactangle: "+r2.getArea());

}
}
```

### 4.Create a class Circle that encapsulates the properties of a circle.
```java
import java.util.*;

class Circle{
    private double radius;

   
    Circle(double radius){
        this.radius=radius;
    }
    
    public double getArea(){
        return Math.PI * Math.pow(radius,2);
    }
    public double getCircum(){
        return 2* Math.PI * radius;
    }
   
}
class Main {
     public static void main(String[] args) {
      Circle c=new Circle(1.0);

      System.out.printf("Area: %.2f\n",c.getArea());
      System.out.printf("Circumference: %.2f",c.getCircum());

}
}
```
### 5. Complete the code by creating the constructor and the getter functions for a class Dog as defined below.
```java
import java.util.*;

class Dog{
    private String name;
    private String breed;
    private int age;
    private String color;

   
    Dog(String name,String breed,int age,String color){
        this.name=name;
        this.breed=breed;
        this.age=age;
        this.color=color;
    }
    
    public String getName(){
        return name;
    }
    public String getBreed(){
        return breed;
    }
    public int getAge(){
        return age;
    }
    public String getColor(){
        return color;
    }
   
}
class Main {
     public static void main(String[] args) {
      Dog d=new Dog("Jackie","Doberman",3,"Brown");

    System.out.println("hi my name is: " + d.getName());
        System.out.println("My breed is : "+d.getBreed());

    System.out.println("My age is: "+d.getAge());

    System.out.println("My color is: "+d.getColor());

}
}
```

## WEEK-3

### 1.Create a class Department having a method getCourses that prints "These are the department's courses". 
```java
import java.util.*;

class Department{
   public void getCourses(){
       System.out.println("These are the department's courses");
   }
}

class ComputerScience extends Department{
    public void getCourses(){
        System.out.println("Courses: Data Structures, Algorithms, Operating Systems");
    }
}
class MechanicalEngineering extends Department{
    public void getCourses(){
        System.out.println(" Courses: Thermodynamics, Fluid Mechanics, Heat Transfer");
    }
}
   
  
class Main {
     public static void main(String[] args) {
      Department d=new Department();
    Department d1=new ComputerScience();
      MechanicalEngineering d2=new MechanicalEngineering();
      

    d.getCourses();
    d1.getCourses();
    d2.getCourses();

        

}
}
```
### 2.There are two class cls1 and cls2 which is subclass of cls1.  cls1 having a method "add" which add two numbers. 
```java
import java.util.*;

class cls1{
   public int add(int a,int b){
       return a+b;
   }
}

class cls2 extends cls1{
    public int mul(int a,int b){
        return a*b;
        
    }
     public int task(int a,int b){
         return (int) (Math.pow(a,2) + Math.pow(b,2));
    }
}

  
class Main {
     public static void main(String[] args) {
         Scanner scan=new Scanner(System.in);
      cls2 c=new cls2();
      int a=scan.nextInt();
      int b=scan.nextInt();
      
      System.out.println(c.add(a,b));
      System.out.println(c.mul(a,b));
      System.out.println(c.task(a,b));

}
}
```
### 3.Write a program to print the factorial of a number by defining a recursive method named 'Factorial'.
```java
import java.util.*;
class Main {
     public static void main(String[] args) {
         Scanner scan=new Scanner(System.in);
   
      int a=scan.nextInt();
      int mul=1;
    for(int i=1;i<=a;i++){
        mul*=i;
    }
      
      System.out.println(mul);

}
}
```
### 4.Write a program to take integer inputs from user until he/she presses q ( Ask to press q to quit after every integer input ). Print average and product of all numbers.
```java
import java.util.*;
class Main {
     public static void main(String[] args) {
         Scanner scan=new Scanner(System.in);
   
     String choice="";
     int sum=0;int count=0;
      int mul=1;
   while(!choice.equals("q")){
       choice=scan.next();
       if(!choice.equals("q")){
           int number=Integer.parseInt(choice);
           sum+=number;
           mul*=number;
           count++;
           
       }
       
   }
      
      System.out.println("product is: "+ mul+"\n Average is: "+((float)sum/count));

}
}
```
### 5.Write a Java program to create a class called Employee with methods called work() and getSalary().
```java
import java.util.*;
class Employee{
    private final int salary;
    
    public Employee(int salary){
        this.salary=salary;
    }
    public void work(){
        System.out.println("working as an employee!");
        
    }
    public int getSalary(){
        return salary;
        
    }
}
class HRManager extends Employee{
    public HRManager (int salary){
        super(salary);
    }
    public void work(){
        System.out.println("Managing employees");
        
    }

    public void addEmployee(){
        System.out.println("Adding new employee");
        
    }
}
class Main {
     public static void main(String[] args) {
         Scanner scan=new Scanner(System.in);
         
         Employee e=new Employee(4000);
         e.work();
         System.out.println("Employee salary: "+ e.getSalary());
         
         HRManager m=new HRManager(7000);
         m.work();
        System.out.println("Manager salary: "+ m.getSalary());
        m.addEmployee();

         
   
    

}
}
```
