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

## WEEK-4
### 1.Complete the code segment to swap two numbers using call by object reference.
```java
import java.util.*;

class Question{
    Scanner scan=new Scanner(System.in);
	    int a=scan.nextInt();
	    int b=scan.nextInt();
    
}

public class Main
{
    public static void swap(Question t){
        int temp=t.a;
        t.a=t.b;
        t.b=temp;
    }
	public static void main(String[] args) {
	    Question t=new Question();
	    
	    System.out.println("Before swap: "+t.a+" "+t.b);

	    swap(t);
	    System.out.println("After swap: "+t.a+" "+t.b);
	}
}
```
### 2. find slope
```java
import java.util.*;

class Point{
    private double x;
    private double y;
    public Point(double x,double y){
        this.x=x;
        this.y=y;
    }
    public double slope(Point p2){
        double slope;
        slope=(p2.y -y )/(p2.x -x);
        return slope;
        
    }
    
   
}

public class Main
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	    double x1=scan.nextInt();
	    double y1=scan.nextInt();
	    double x2=scan.nextInt();
	    double y2=scan.nextInt();
    
	    Point p1=new Point(x1,y1);
	    Point p2=new Point(x2,y2);
	    
	    System.out.print("Slope: "+p1.slope(p2));
	    
	   
	}
}
```
### 3.sum and product
```java
import java.util.*;

class Hello{
    
    static int sum(int a,int b){
        return a+b;
    }
    static int multiply(int a,int b){
        return a*b;
    }
    
   
}

public class Main
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	    int a=scan.nextInt();
	    int b=scan.nextInt();
	    
	    Hello h=new Hello();
	    
	    System.out.println("Sum: "+h.sum(a,b));
	    System.out.println("Multiply: "+h.multiply(a,b));
	 
    
	  
	    
	   
	}
}
```

###
```java
import java.util.*;

interface ExtraLarge{
    static String extra="This is extra";
    void display();
}

class Large{
    
   public void print(){
       System.out.println("This is large");
   }
}

class Medium extends Large{
    public void print(){
        super.print();
        System.out.println("This is medium");
    }
}
class small extends Medium{
    public void print(){
        super.print();
        System.out.println("This is small");
    }
}

public class Main implements ExtraLarge
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	     
	     small s=new small();
	     s.print();
	    Main m=new Main();
	    m.display();
	    
	    
	   
	}
	public void display(){
	    System.out.println(extra);
	}
}
```

### 5.Consider First n even numbers starting from zero(0).Complete the code segment to calculate sum of  all the numbers divisible by 3 from 0 to n. Print the sum.
```java
import java.util.*;


public class Main 
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	     
	     int n=scan.nextInt();
	     int sum=0;
	     int result=1;int i=0;
	     while(result<=n){
	         if(i%2==0 ){
	             if(i%3==0){
	                   sum+=i; 
	             }
	              result++;
	         }
	         i++;
	     }
	     System.out.println(sum);
	}

}
```

## WEEK-5

### 1.Write a program to create a method that takes an integer as a parameter and throws an exception if the number is odd.

```java
import java.util.*;


public class Main 
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	     
	     int n=scan.nextInt();
	    trynumber(n);
	    
	}
	
	public static void trynumber(int n){
	    try{
	        checkEvenNumber(n);
	        System.out.print(n +"it is even");
	    }
	    catch (IllegalArgumentException e){
	        System.out.print("Error: "+ e.getMessage());
	    }
	}
	
	public static void checkEvenNumber(int n) throws IllegalArgumentException{
	    if(n%2!=0){
	        throw new IllegalArgumentException(n +"is odd");
	    }
	}

}
```

### 2.

```java
import java.util.*;

interface Searchable{
    boolean search(String keyword);
}
class Document implements Searchable{
    private String content;
    public Document(String content){
        this.content=content;
    }
    public boolean search(String keyword){
        return content.contains(keyword);
    }
    
}
class WebPage implements Searchable{
    private String url;
    private String htmlContent;
    public WebPage(String url,String htmlContent){
        this.url=url;
        this.htmlContent=htmlContent;
        
        
    }
    
    public boolean search(String keyword){
        return htmlContent.contains(keyword);
    }
    
}

public class Main 
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	   String text=scan.nextLine();
	   String document=text;
	   String str=scan.nextLine();
	   Document d=new Document(document);
	   
	   boolean documentContainsKeyword= d.search(str);
	   System.out.println("Document contains keyword: " +str+ " "+documentContainsKeyword);

        WebPage webPage = new WebPage("https://onlinecourses.nptel.ac.in", "This is a NPTEL online course webpage.");

	   	   boolean webPageContainsKeyword= webPage.search(str);
        System.out.print("Webpage contains keyword 'webpage': " + webPageContainsKeyword);

	}
	
}
```

### 3.Write a  program to create a method that takes a string as input and throws an exception if the string does not contain vowels.
(Note: Check both upper and lower case vowels)
```java
import java.util.*;

class NoVowelsException extends Exception{
    public NoVowelsException(String message){
        super(message);
    }
}
public class Main 
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	  try{
	      String text=scan.nextLine();
	      
	      System.out.println("Original String: "+text);
	      
	      checkVowels(text);
	      System.out.println("String contains vowels");
	  }
	  catch(NoVowelsException  e){
	      System.out.println("Error: "+e.getMessage());
	  }
	}
	public static void checkVowels(String text) throws NoVowelsException{
	    if(!text.toLowerCase().matches(".*[aeiou].*")){
	        throw new NoVowelsException("String does not conatin any vowels");
	    }
	}
	
}
```

### 4.Write a  program to create an interface Flyable with a method called fly_obj().
```java
import java.util.*;

interface Flyable{
    public void fly_obj();
}
class Spacecraft implements Flyable{
    public void fly_obj(){
        System.out.println("Spacecraft is flying");
    }
    
}
class Airplane implements Flyable{
    public void fly_obj(){
        System.out.println("Aeroplane is flying");
    }
    
}
class Helicopter implements Flyable{
    public void fly_obj(){
        System.out.println("Helicopter is flying");
    }
    
}
public class Main 
{
   
	public static void main(String[] args) {
	     Scanner scan=new Scanner(System.in);
	     
	    /* Flyable f=new Spacecraft();
	     Flyable f1=new Airplane();
	     Flyable f2=new Helicopter();
	     */
	     
	     Flyable[] fff={new Spacecraft(),new Airplane(),new Helicopter()};
	     
	    /* f.fly_obj();
	     f1.fly_obj();
	     f2.fly_obj();*/
	     
	     for(Flyable obj:fff){
	         obj.fly_obj();
	     }
	     
	  
	}
	
	
}
```
### 5. Write a program to create an interface Playable with a method play() that takes no arguments and returns void.

(same as previous question)

```java
interface Playable {
    void play();
}
class Football implements Playable {
  public void play() {
    System.out.println("Playing football");
  
  }
}
class Volleyball implements Playable {
    public void play() {
        System.out.println("Playing volleyball");
    }
}
class Basketball implements Playable {
    public void play() {
        System.out.print("Playing basketball");
    }
}
public class Main {
    public static void main(String[] args) {
        Playable football = new Football();
        Playable volleyball = new Volleyball();
        Playable basketball = new Basketball();
        football.play();
        volleyball.play();
        basketball.play();
    }
}
```

## WEEK-6
### 1.find square 
```java
import java.util.*;

interface Number_{
    int findsqrt(int i);
}
class A implements Number_{
    int square;int n;
    public int findsqrt(int n){
        square=n*n;
        return square;
    }
    
}

public class Main
{
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		int n=scan.nextInt();
		A a=new A();
		
		System.out.println(a.findsqrt(n));
	}
}
```
### 2. find GCD

```java
import java.util.*;

interface GCD{
    int findGCD(int n1,int n2);
}
class A implements GCD{
    int n1;int n2;
    public int findGCD(int n1,int n2){
        if(n1==0 && n2==0){
            return -1;
            
        }
        else if (n2==0){
            return n1;
        }
        else{
            return findGCD(n2,n1%n2);
        }
    }
    
}

public class Main
{
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		int n1=scan.nextInt();
		int n2=scan.nextInt();
		A a=new A();
		
		System.out.println(a.findGCD(n1,n2));
	}
}
```
### 3.thread  class

```java
import java.util.*;
public class Main extends Thread
{
    public void run(){
        System.out.print("thread is running");
    }
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		
		Main m=new Main();
		m.start();
		
	}
}
```
### 4.synchronized method
```java
import java.util.*;

class Execute{
  synchronized   void print(int n){
        for(int i=1;i<=5;i++){
            System.out.println(n*i);
            try{
                Thread.sleep(400);
            }
            catch(Exception e){
                System.out.println(e);
            }
        }
    }
}
class Thread1 extends Thread{
    Execute t;
    Thread1(Execute t){
        this.t=t;
    }
    public void run(){
        t.print(5);
    }
}
class Thread2 extends Thread{
    Execute t;
    Thread2(Execute t){
        this.t=t;
    }
    public void run(){
        t.print(10);
    }
}


public class Main 
{
  
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		Execute obj=new Execute();
		Thread1 t1=new Thread1(obj);
		Thread2 t2=new Thread2(obj);
		t1.start();
		t2.start();
	
		
	}
}
```
### 5.Name of thread

```java
import java.util.*;



public class Main extends Thread
{
    public void run(){
        System.out.println("Thread is running");
    }
  
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		 
		 Main m=new Main();
		 
		 System.out.println("Name of thread 't': "+m.getName());
		 
		 m.start();
		 
		 m.setName("Kaviya");
		 
		 System.out.println("New name of thread 't' : "+m.getName());
	
		
	}
}
```

## WEEK-7

### 1.longest word
```java
import java.util.*;



public class Main 
{
    
    public static String findLongestWord(String text){
        String longestWord="";
        String[] words=text.split("\\s+");
        
        for(String word: words){
            if(word.length()>longestWord.length()){
                longestWord=word;
            }
        }
        return longestWord;
    }
  
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		 
		 String text=scan.nextLine();
		 System.out.println("The longest word in the text is: "+ findLongestWord(text));
		
	}
}
```
### 3.remove element
```java
import java.util.*;



public class Main 
{
    public static int[] removeAll(int[] arr,int remove){
        ArrayList<Integer> temp=new ArrayList<>();
        
        for(int i=0;i<arr.length;i++){
            if(arr[i]!=remove){
                temp.add(arr[i]);
            }
        }
        int [] result=new int[temp.size()];
        for(int i=0;i<temp.size();i++){
            result[i]=temp.get(i);
        }
        return result;
    }
   
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		 
		int n=scan.nextInt();
		int[] arr=new int[n];
		for(int i=0;i<n;i++){
		    arr[i]=scan.nextInt();
		}
		int remove=scan.nextInt();
		
		System.out.println("Original Array: " + Arrays.toString(arr));
		arr=removeAll(arr,remove);
		System.out.println("Array after removing: " + remove+" "+ Arrays.toString(arr));
		
		
	}
}
```

### 4.check prime
```java
import java.util.*;



public class Main 
{
    public static boolean isprime(int a){
        if(a<=1){
            return false;
        }
        for(int i=2;i<=a/2;i++){
            if(a%i==0){
                return false;
            }
        }
        return true;
    }
   
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		 
		int n1=scan.nextInt();
		int n2=scan.nextInt();
		int sum=0;
		
		for(int i=n1;i<=n2;i++){
		    if(isprime(i)){
		        sum+=i;
		    }
		}
	
		System.out.println(sum);
		
	}
}
```
### 5. even thread and odd thread

```java
import java.util.*;
class PrintNumbers implements Runnable{
    private int start;
    private int end;
    public PrintNumbers(int start,int end){
        this.start=start;
        this.end=end;
    }
    public void run(){
        for(int i=start;i<=end;i+=2){
            System.out.println(Thread.currentThread().getName()+": "+i);
        }
    }
}



public class Main 
{
  
   
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		 
		int evenStart=scan.nextInt();
		int evenEnd=scan.nextInt();
		int oddStart=scan.nextInt();
		int oddEnd=scan.nextInt();
		
		Thread evenThread=new Thread(new PrintNumbers(evenStart,evenEnd),"evenThread");
		Thread oddThread=new Thread(new PrintNumbers(oddStart,oddEnd),"oddThread");
		
		evenThread.start();
		try{
		    Thread.sleep(500);
		}
		catch (InterruptedException e){
		    e.printStackTrace();
		}
		
		oddThread.start();
		
	
		
	}
}
```
## WEEK-8

### 1.get current year and month

```java
import java.util.*;

public class Main 
{
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		int year;
		java.util.Calendar current;
		
		current=java.util.Calendar.getInstance();
		year=current.get(current.YEAR);
		
		System.out.println("Current year: "+year);

		System.out.println("Current Month: "+10);
		
	}
}
```
### 2.Complete the code segment to call the default method in the interface First and Second.
```java
import java.util.*;
interface First{
    default void show(){
        System.out.println("Default method implementation of First interface.");
    }
}
interface Second{
    default void show(){
        System.out.println("Default method implementation of Second interface.");
    }
}


public class Main implements First,Second
{
    public void show(){
        First.super.show();
        Second.super.show();
    }
	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		
		Main m=new Main();
		m.show();
		
	}
}
```
### 3.
```java
interface ShapeX {
 public String base = "This is Shape1";
 public void display1();
}

interface ShapeY extends ShapeX {
 public String base = "This is Shape2";
 public void display2();
}

class ShapeG implements ShapeY {
 public String base = "This is Shape3";
 public void display1() {
  System.out.println("Circle: " + ShapeX.base);
 }
 public void display2() {
  System.out.print("Circle: " + ShapeY.base);
 }
}
public class Main{
 public static void main(String[] args) {
  ShapeG circle = new ShapeG();
  circle.display1();
  circle.display2();
 }
}
```

### 4.there is a way to print without using “System”

(Hint: Use Static import)
```java
import java.util.Scanner;
import static java.lang.System.*;
public class Main{
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    String courseName = scanner.nextLine(); 
    out.print("Course: " + courseName); 
  }
}
```
### 5.You have to complete the code using ONLY ONE try-catch block to handle all the possible exceptions.
```java
import java.util.Scanner;
public class Main{
      public static void main (String   args[ ] ) {
		Scanner scan = new Scanner(System.in);
          int i=scan.nextInt();
          int j;
try {
				switch (i) {
				case 0 : 
					int zero = 0; 
					j = 92/ zero; 		
					break;
				case 1: 
					int b[ ] = null; 
					j = b[0] ; 	
					break;
				default:
				    System.out.print("No exception");
				} 		
			}
            // catch block			
			catch (Exception e) {		
				System.out.print(e) ;
			}
}
}
```

## WEEK-9

### 1.pattern printing
```java
import java.util.Scanner;
class W09_P1 {
  public static void main(String args[]) 
    {
        Scanner in = new Scanner(System.in);
        //System.out.print("Input the number:  ");
        int n = in.nextInt();
int count = 1;
        int no_of_spaces = 1;
        int start = 0;

        for (int i = 1; i < (n * 2); i++) 
        {

            for (int spc = n - no_of_spaces; spc > 0; spc--) 
            {
                System.out.print(" ");
            }
            if (i < n) 
            {
                start = i;          //for number
                no_of_spaces++;    //for spaces
            } else 
            {
                start = n * 2 - i;   //for number
                no_of_spaces--;      //for space
            }
            for (int j = 0; j < count; j++) 
            {
                System.out.print(start);
                if (j < count / 2) 
                {
                    start--;
                } else 
                {
                    start++;
                }
            }
            if (i < n)
            {
                count = count + 2;
            } else {
                count = count - 2;
            }

            System.out.println();
        }
}
}
```
### 2.abstract class
```java
abstract class Person {
    public abstract void eat();
    public abstract void sleep();
    public abstract void exercise();
  }
class Athlete extends Person {
    @Override
    public void eat() {
      System.out.println("Athlete: Include foods full of calcium, iron, potassium, and fiber.");
    }

    @Override
    public void sleep() {
      System.out.println("Athlete: sleeps for 8 hours.");
    }
  
    @Override
    public void exercise() {
      System.out.println("Athlete: Training allows the body to gradually build up strength and endurance, improve skill levels and build motivation, ambition and confidence.");
    }
  }

  class LazyPerson extends Person {
    @Override
    public void eat() {
      System.out.println("Couch Potato: Eating while watching TV also prolongs the time period that we're eating.");
    }

    @Override
    public void sleep() {
      System.out.print("Couch Potato: sleeps for 12 hours.");
    }
  
    @Override
    public void exercise() {
      System.out.println("Couch Potato: Rarely exercising or being physically active.");
    }
  }
public class W09_P2 {
    public static void main(String[] args) {
      Person athlete = new Athlete();
      Person lazyPerson = new LazyPerson();
      athlete.eat();
      athlete.exercise();
      athlete.sleep();
      lazyPerson.eat();
      lazyPerson.exercise();
      lazyPerson.sleep();
    }
  }
```
### 3.Write a Java program to create a base class Shape with methods draw() and calculateArea().
```java
import java.util.Scanner;
abstract class Shape {
    public abstract void draw();
  
    public abstract double calculateArea();
  }
class Circle extends Shape {
    private double radius;
  
    public Circle(double radius) {
      this.radius = radius;
    }
  
    @Override
    public void draw() {
      System.out.println("Drawing a circle");
    }
  
    @Override
    public double calculateArea() {
      return Math.PI * radius * radius;
    }
  
    protected double getRadius() {
      return radius;
    }
  }
  //Cylinder.java
  class Cylinder extends Circle {
    private double height;
  
    public Cylinder(double radius, double height) {
      super(radius);
      this.height = height;
    }
  
    @Override
    public void draw() {
      System.out.println("Drawing a cylinder");
    }
  
    @Override
    public double calculateArea() {
      // Calculate the total surface area of the cylinder (including the circular top and bottom)
      double circleArea = super.calculateArea();
      double sideArea = 2 * Math.PI * getRadius() * height;
      return 2 * circleArea + sideArea;
    }
  }
public class W09_P3{
    public static void main(String[] args) {
      Scanner in = new Scanner(System.in);
      int radius = in.nextInt();
      int height = in.nextInt();

      Shape circle = new Circle(radius);
      Shape cylinder = new Cylinder(radius, height);
  
      drawShapeAndCalculateArea(circle);
      drawShapeAndCalculateArea(cylinder);
    }
  
    public static void drawShapeAndCalculateArea(Shape shape) {
      shape.draw();
      double area = shape.calculateArea();
      System.out.printf("Area: %.4f%n", area);
    }
  }
```

### 4.
```java
import java.util.Scanner;
class ElectronicsProduct {
    // Attributes for the product ID, name, and price
    private String productId;
    private String name;
    private double price;

    // Constructor to initialize the ElectronicsProduct object
    public ElectronicsProduct(String productId, String name, double price) {
        this.productId = productId;
        this.name = name;
        this.price = price;
    }

    // Method to apply a discount to the product price
    public void applyDiscount(double discountPercentage) {
        // Calculate the discount amount
        double discountAmount = price * discountPercentage / 100;
        // Subtract the discount amount from the original price
        price -= discountAmount;
    }

    // Method to calculate the final price after discount
    public double getFinalPrice() {
        // Return the current price which may have been discounted
        return price;
    }

    // Getter for product ID
    public String getProductId() {
        return productId;
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Getter for price
    public double getPrice() {
        return price;
    }
}
class WashingMachine extends ElectronicsProduct {
    // Additional attribute for the warranty period
    private int warrantyPeriod; // in months

    // Constructor to initialize the WashingMachine object
    public WashingMachine(String productId, String name, double price, int warrantyPeriod) {
        // Call the superclass constructor to initialize common attributes
        super(productId, name, price);
        this.warrantyPeriod = warrantyPeriod;
    }

    // Method to extend the warranty period
    public void extendWarranty(int additionalMonths) {
        // Add the additional months to the current warranty period
        warrantyPeriod += additionalMonths;
    }

    // Getter for warranty period
    public int getWarrantyPeriod() {
        return warrantyPeriod;
    }

    // Override the display method to include warranty period
    @Override
    public void applyDiscount(double discountPercentage) {
        // Call the superclass method to apply the discount
        super.applyDiscount(discountPercentage);
        // Display a message indicating the discount was applied
        System.out.println("Discount applied to Washing Machine: " + getName());
    }
}
public class W09_P4{
    public static void main(String[] args) {
        // Create an ElectronicsProduct object
        ElectronicsProduct product = new ElectronicsProduct("WM123", "Washing Machine", 1.00);
        // Apply a discount and display the final price
        product.applyDiscount(10);
        //System.out.println("Product ID: " + product.getProductId());
        //System.out.println("Name: " + product.getName());
        //System.out.println("Price after discount: $" + product.getFinalPrice());
        //System.out.println();

        // Create a WashingMachine object
        Scanner in = new Scanner(System.in);

        String productId = in.nextLine();     
        String name = in.nextLine();
        int price = in.nextInt();
        int warrantyPeriod = in.nextInt();
        
        int discountPercentage = in.nextInt();

        WashingMachine washingMachine = new WashingMachine(productId,name,price,warrantyPeriod);
        // Apply a discount and display the final price
        washingMachine.applyDiscount(discountPercentage);
        System.out.println("Product ID: " + washingMachine.getProductId());
        System.out.println("Name: " + washingMachine.getName());
        System.out.println("Price after discount: $" + washingMachine.getFinalPrice());
        // Display the warranty period
        System.out.println("Warranty period: " + washingMachine.getWarrantyPeriod() + " months");

        // Extend the warranty period and display the new warranty period
        washingMachine.extendWarranty(12);
        System.out.print("Warranty period after extension: " + washingMachine.getWarrantyPeriod() + " months");
    }
}
```
### 5.Write a Java program to find the length of the longest sequence of zeros in binary representation of an integer.
```java
import java.util.Scanner;
public class W09_P5{
static int maxZeros(int N) {
                // variable to store the length of
                        // longest consecutive 0's
                        int maxm = -1;

                        // to temporary store the consecutive 0's
                        int cnt = 0;

                        while (N != 0) {
                                if ((N & 1) == 0) {
                                        cnt++;
                                        N >>= 1;
                                        maxm = Math.max(maxm, cnt);
                                } else {

                                        maxm = Math.max(maxm, cnt);
                                        cnt = 0;
                                        N >>= 1;
                                }
                        }
                        return maxm;
                }
public static void main(String args[]) {
                Scanner in = new Scanner(System.in);

                int n = in.nextInt();
                System.out.print(maxZeros(n));

        }
  
}
```
