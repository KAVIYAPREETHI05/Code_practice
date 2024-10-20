# WEEK-1

1.Which of the following is not a valid comment in Java?

 a. /** comment */

 b. /* comment */
 
 c. /* comment /
 
 d. // comment

**Answer:c. /* comment /**

2. What is the output of the following code?

```java
public class Main {

public static void main(String[] args) {

String str1 = "NPTEL";

String str2 = "java";

int a = 20;

int b = 24;

System.out.println(str1 + a + b); // Statement 1

System.out.println(a + b + str2); // Statement 2

}

}
```
  a. NPTEL2024
         44java
         
  b. NPTEL44
         44java
 
  c. NPTEL2024
         2024java
 
  d. NPTEL44
         2024java

**Answers:
a. NPTEL2024
         44java**

3.Which of the following is used to find and fix bugs in the Java programs?

  a. JVM

  b. JRE
 
  c. JDK
 
  d. JDB

**Answers:
d. JDB**

4.What is the value returned by the method f() defined below ?

```java
public static int f(int x, int y){return (x>y) ? y : x;}

```
 a. The sum of x and y, that is, x + y.

 b. The difference of x and y, that is, x - y.

 c. The maximum of x and y, that is, the larger value of x and y.

 d. The minimum of x and y, that is, the smaller value of x and y.

**Answers:
d. The minimum of x and y, that is, the smaller value of x and y.**

5.Consider the following program. What will be the output of the program if it is executed?

```java
public class Question {

  public static void main(String args[]) {

    int f = 0, g = 1;

    for (int i = 0; i <= 5; i++) {

      System.out.println(f);

      f = f + g;

      g = f - g;

    }

  }

}
```

 a. Print first six even numbers.

 b. Print first six odd numbers.

 c. Print first six prime numbers.

 d. Print first six Fibonacci numbers.

**Answers:
d. Print first six Fibonacci numbers.**

6.Which program is used to compile Java source code into bytecode?
 a. javap
 
 b. javac
 
 c. java
 
 d. javad
**Answers:
b. javac**

7.Consider the following program.

```java
public class Question {

  public static void main(String[] args) {

    int x = 5;

    x *= (2 + 8);

    System.out.println(x);

  }

}
```
 a. 50
 
 b. 10
 
 c. Compiler error
 
 d. 5

**Answers:
a. 50**

8.What is the incorrect statement about bytecode?

 a. Java when compiles the source code, it converts it to bytecode.
 
 b. JVM (Java Virtual Machine) is an interpreter of bytecode.
 
 c. Bytecode is not portable and it needs to be compiled separately for each platform.
 
 d. JVM offers a protected environment which helps in enhanced safety for the system.

**Answers:
c. Bytecode is not portable and it needs to be compiled separately for each platform.**

9.In Java, what is the role of the public static void main(String[] args) method?
 
 a. Initialization method
 
 b. Execution entry point
 
 c. Constructor
 
 d. Destructor

**Answers:
b. Execution entry point**

10.What is the purpose of the break statement in Java?
 
 a. To terminate the program
 
 b. To exit a loop or switch statement
 
 c. To skip the next iteration of a loop
 
 d. To return a value from a method

**Answers:
b. To exit a loop or switch statement**

# WEEK-2

1.Which of the following is the correct way to declare a class in Java?
 
 a. public class MyClass {}
 
 b. class MyClass[] {}
 
 c. public MyClass class {}
 
 d. MyClass public class {}

**Answers:
a. public class MyClass {}**

2.What is the purpose of a constructor in a class?
 
 a. To destroy objects of the class
 
 b. To create static methods
 
 c. To implement inheritance
 
 d. To initialize objects of the class

**Answers:
d. To initialize objects of the class**

3.Which keyword is used in Java to refer to the current object?
 
 a. that
 
 b. self
 
 c. current
 
 d. this

**Answers:
d. this**

4.Consider the following code snippet. What will be the output?
```java
class NPTEL_W2 {
  int x;
  NPTEL_W2(int x) {
     this.x = x;
  }
  void printX() {
      System.out.println(this.x);
  }
  public static void main(String[] args) {
      NPTEL_W2 obj = new NPTEL_W2(10);
      obj.printX();
  }
}
```
 
 a. 0
 
 b. 10
 
 c. Compilation error
 
 d. Runtime error

**Answers:
b. 10**

5.Which of the following demonstrates constructor overloading in Java?
 
 a. Defining multiple constructors in a class with different parameter lists
 
 b. Defining multiple methods in a class with the same name
 
 c. Defining a constructor in a subclass
 
 d. Using the super keyword

**Answers:
a. Defining multiple constructors in a class with different parameter lists**

6.What is the purpose of the this keyword in the context of avoiding name space collision?
 
 a. To call another constructor in the same class
 
 b. To refer to the current object
 
 c. To differentiate between instance variables and parameters with the same name
 
 d. To import another class

**Answers:
c. To differentiate between instance variables and parameters with the same name**

7.Which of the following is the correct signature of the main method in Java?
 
 a. public void main(String[] args)
 
 b. public static void main(String[] args)
 
 c. public static void main()
 
 d. public main(String[] args)

**Answers:
b. public static void main(String[] args)**

8.Which class is used in Java to take runtime data input from the user?
 
 a. BufferReader
 
 b. UserInputStreamReader
 
 c. Scanner
 
 d. DataInputStreamReader

**Answers:
c. Scanner**

9.What is the output of the following Java code snippet? (\n in output is to be assumed to be the new line character)
```java
public class Main {

  public static void main(String[] args) {

    System.out.print("Hello ");

    System.out.println("World");

    System.out.printf("Number: %d", 10);

  }

}
```
 
 a. Hello World\nNumber: 10
 
 b. Hello WorldNumber: 10
 
 c. Hello \nWorld\nNumber: 10
 
 d. Hello World\nNumber: 10\n

**Answers:
a. Hello World\nNumber: 10**

10.How do you read a line of text from the console using the Scanner class in Java?
 
 a. scanner.readLine()
 
 b. scanner.nextLine()
 
 c. scanner.getLine()
 
 d. scanner.fetchLine()

**Answers:
b. scanner.nextLine()**





























