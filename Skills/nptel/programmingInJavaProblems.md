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
