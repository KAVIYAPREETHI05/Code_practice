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

# WEEK-3

1.What will be the output of the following program?

```java
class First {
    static void staticMethod() {
        System.out.println("Static Method");
    }
}
class MainClass {
    public static void main(String[] args) {
        First first = null;
        First.staticMethod();
    }
}
```

 a. Static Method
 
 b. Throws a NullPointerException
 
 c. Compile-time error
 
 d. Run time error

**Answers:
a. Static Method**

2.What will be the output of the below program.

```java
class superDemoClass {
    final int a = 20;
}
class subDemoClass extends superDemoClass {
    void subFunc() {
        a = 40;
        System.out.println("value of a = " + a);
    }
}
class demo {
    public static void main(String[] args) {
        subDemoClass subc = new subDemoClass();
        subc.subFunc();
   }
}
```
 
 a. value of a = 20
 
 b. error: cannot assign a value to final variable ‘a’
 
 c. error: unknown variable 'a' in class subDemoClass
 
 d. value of a = 40

**Answers:
b. error: cannot assign a value to final variable ‘a’**

3.All the variables of interface should be?
 
 a. default and final
 
 b. default and static
 
 c. public, static and final
 
 d. protect, static and final

**Answers:
c. public, static and final**

4.What will be the output of the below program.

```java
class static_out {
    static int x;
    static int y;
    void add(int a, int b) {
        x = a + b;
        y = x + b;
    }
}
public class static_use {
    public static void main(String args[]) {
        static_out obj1 = new static_out();
        static_out obj2 = new static_out();
        int a = 2;
        obj1.add(a, a + 1);
        obj2.add(5, a);
        System.out.println(obj1.x + " " + obj2.y);
  }
}
```
 a. 7 7.4
 
 b. 6 6.4
 
 c. 7 9
 
 d. 9 7

**Answers:
c. 7 9**

5.What will be the output of the below program.
```java
class access {
    public int x;
    private int y;
    void cal(int a, int b) {
        x = a + 1;
        y = b;
    }
    void print() {
        System.out.println(" " + y);
    }
}
public class access_specifier {
    public static void main(String args[]) {
        access obj = new access();
        obj.cal(2, 3);
        System.out.print(obj.x);
        obj.print();
    }
}
```

 a. 2 3
 
 b. 3 3
 
 c. Runtime Error
 
 d. Compilation Error

**Answers:
b. 3 3**

6.If a variable of primitive datatype in Java is declared as final, then
 
 a. It cannot get inherited
 
 b. Its value cannot be changed
 
 c. It cannot be accessed in the subclass
 
 d. All of the above

**Answers:
b. Its value cannot be changed**

7.Members which are not intended to be inherited are declared as
 
 a. Public members
 
 b. Protected members
 
 c. Private members
 
 d. Private or Protected members

**Answers:
c. Private members**

8.If a base class is inherited in protected access mode then which among the following is true?
 
 a. Public and Protected members of base class becomes protected members of derived class
 
 b. Only protected members become protected members of derived class
 
 c. Private, Protected and Public all members of base, become private of derived class
 
 d. Only private members of base, become private of derived class

**Answers:
a. Public and Protected members of base class becomes protected members of derived class**

9.Which type of inheritance leads to diamond problem?
 
 a. Single level
 
 b. Multi-level
 
 c. Multiple
 
 d. Hierarchical

**Answers:
c. Multiple**

10.What will be the output of the below program.
```java
class superDemoClass {

    final void func() {

        int a = 20;

        System.out.println("value of a = " + a);

    }

}

 

class subDemoClass extends superDemoClass {

    void func() {

        int b = 60;

        System.out.println("value of b = " + b);

    }

}

 

class demo {

    public static void main(String[] args) {

        subDemoClass subc = new subDemoClass();

        subc.func();

    }

}
```
 
 a. error: func() in subDemoClass cannot override func() in superDemoClass
 
 b. value of b = 60
 
 c. value of a = 20
 
 d. None of the above

**Answers:
a. error: func() in subDemoClass cannot override func() in superDemoClass**

# WEEK-4

1.Which of these access specifiers must be used for main() method?
 
 a. private
 
 b. public
 
 c. protected
 
 d. default

**Answers:
b. public**

2.What is the output of the below Java Code Snippet with protected access modifier?
```java
// Teacher.java ------------------
package nptel1;
public class Teacher {
  protected void showMarks() {
    System.out.println("100 Marks");
  }
}
```
```java
// Student.java ------------------
package nptel2;
import nptel1.*;
public class Student extends Teacher {
  void show() {
    showMarks();
  }
  public static void main(String[] args) {
    Student st1 = new Student();
    st1.show();
  }
}
```
 a. 100 marks
 
 b. No output
 
 c. Compiler error
 
 d. None of the above

**Answers:
a. 100 marks**

3.What is the process by which we can control what parts of a program can access the members of a class?
 
 a. Polymorphism
 
 b. Augmentation
 
 c. Encapsulation
 
 d. Recursion

**Answers:
c. Encapsulation**

4.Consider the 2 programs:

```java
// Main1.java ------------------

public class Main1{

    public static void main(String args[]){  

        int number = 10;

        System.out.println(number++ + ++number);

    }

}
```
```java
// Main2.java ------------------

public class Main2{

    public static void main(String args[]){  

        int number = 10;

        System.out.println(++number + number++);

    }

}
```
 
 a. Both pre-increment and post-increment operators becomes pre-increment during print.
 
 b. Both pre-increment and post-increment operators becomes post-increment during print.
 
 c. Both Main1 and Main2 classes give the same output.
 
 d. Pre-increment and post-increment operators don’t work during print.

**Answers:
c. Both Main1 and Main2 classes give the same output.**

5.Which is the least restrictive access modifier in Java?
 
 a. public
 
 b. private
 
 c. protected
 
 d. default

**Answers:
a. public**

6.Choose the correct syntax of a Java Package below.
 
 a. package PACKAGE_NAME;
 
 b. package PACKAGE_NAME.*;
 
 c. pkg PACKAGE_NAME;
 
 d. pkg PACKAGE_NAME.*;

**Answers:
a. package PACKAGE_NAME;**

7.What is the default package in Java?
 
 a. It is a package that contains all built-in classes.
 
 b. It is a package that needs to be defined as default.
 
 c. It is a package that does not have a name.
 
 d. It is a package used for importing external libraries.
Yes, the answer is correct.
Score: 1
Accepted Answers:
c. It is a package that does not have a name.

8.A package is a collection of:
 
 a. classes
 
 b. interfaces
 
 c. editing tools
 
 d. classes and interfaces

**Answers:
d. classes and interfaces**

9/In Java, can a subclass in a different package access a superclass’s protected method?
 
 a. Yes, without any restrictions.
 
 b. Yes, but only if they are in the same package.
 
 c. No, protected methods are not accessible by subclasses.
 
 d. No, protected methods are only accessible within the same class.

**Answers:
b. Yes, but only if they are in the same package.**

10.Consider the program given below. What will be the output if the program is executed?
```java
// Main1.java ------------------

public class Main1{

    public static void main(String args[]){  

        int number = 10;

        System.out.println(number++ + ++number);

    }

}
```
```java
// Main2.java ------------------

public class Main2{

    public static void main(String args[]){  

        int number = 10;

        System.out.println(++number + number++);

    }

}
```
 a. It will give compile-time error
 
 b. It will give run-time error
 
 c. 1.0
 
 d. 3.14

**Answers:
a. It will give compile-time error**

# WEEK-5

1.Which exception will be thrown by parseInt() method in Java?
 
 a. IntegerOutOfBoundException
 
 b. IntegerFormatException
 
 c. ArithmeticException
 
 d. NumberFormatException

**Answers:
d. NumberFormatException**

2.What will be the output of the following program?
```java
interface P {

String p ="PPPP";

String methodP();

}

interface Q extends P {

String q="QQQQ";

String methodQ();

}

class R implements P, Q {

public String methodP() {

return q + p;

}

public String methodQ() {

return p + q;

}

}

public class Main {

public static void main(String[] args) {

Rr= new R();

System.out.println(r.methodP());

System.out.println(r.methodQ());

}

}
```
Answer: QQQQPPPP
PPPPQQQQ

3.what is the output?
```java
class A implements B {

public int methodB(int i) { return i = +i* 1;

}

}

interface B {

int methodB(int i);

}

public class MainClass {

public static void main(String[] args) { B b = new A();

System.out.println(b.methodB(2));

}

}
```
 a. 4
 
 b. 6
 
 c. 2
 
 d. 8

**Answers:
a. 4**

4.A method that potentially generates a checked exception must include this keyword in its method signature:
 
 a. throw
 
 b. extend
 
 c. throws
 
 d. extends

**Answers:
c. throws**

5.Which of the following statements is true about Java's finally block?
 
 a. The finally block is only executed if an exception is thrown in the try block
 
 b. The finally block is only executed if an exception is thrown in the catch block
 
 c. The finally block is only executed if an exception is not thrown in the try or catch block
 
 d. The finally block is executed regardless of whether an exception is thrown in the try or catch block

**Answers:
d. The finally block is executed regardless of whether an exception is thrown in the try or catch block**


6.Which of the following statements is true about exception handling in Java:
 
 a. A try block can have many catch blocks but only one finally block
 
 b. A try block can have many catch blocks and many finally blocks
 
 c. A try block must have one finally block for each catch block
 
 d. A try block must have at least one catch block to have a finally block

**Answers:
a. A try block can have many catch blocks but only one finally block**

7.what is output?
```java
class Output {

public static void main(String args[]) {

try {

int a = 0;

int b = 5;

int c = b/a;

System.out.print("Hello");

} catch (Exception e) {

System.out.print("World");

} finally {

System.out.print("World");

}

7

}

}
```
 a. Hello
 
 b. World
 
 c. HelloWOrld
 
 d. WorldWorld

**Answers:
d. WorldWorld**

8.what is output?
```java
class Output {

public static void main(String args[]) {

try {

int a = 0;

int b = 5;

int ca / b;

System.out.print("Hello");

} finally {

System.out.print("World");

}

}

}
```
 a. Hello
 
 b. World
 
 c. HelloWOrld
 
 d. Compilation Error

**Answers:
c. HelloWOrld**

9.what is output?
```java
interface calculate {
 void cal(int item);
}
class displayA implements calculate { int x;

public void cal(int item) { x =item *item;
}
}
class displayß implements calculate { int x;
public void cal(int item) {
x=item/item;
}
}
class interfaces {
public static void main(String args[]) {
displayA= arr1
displayB =arr2
arr1.x =0;
arr2.x = 0;
arr1.cal(2);
arr2.cal(2);
System.out.print(arr1.x+"" + arr2.x);
new displayA();
new display();
}
}
```
 
 a. 0 0
 
 b. 2 2
 
 c. 4 1
 
 d. 1 4

**Answers:
c. 4 1**

10.Which of the following exceptions is not a subclass of the RuntimeException class?
 
 a. NullPointerException
 
 b. ArrayIndexOutOfBoundsException
 
 c. IOException
 
 d. ArithmeticException

**Answers:
c. IOException**

# WEEK-6

1.what is output?
```java
public class Question {

public static void main(String[] args) {

try {

int a = 5/0;

}

catch (Exception e) {

catch (ArithmeticException a) {

System.out.println("Cannot divide by 0");

}

} System.out.println("Hello World");

}

}
```
 a. “Hello World”
 
 b. “Cannot divide by 0”
 
 c. Compilation Error
 
 d. Runtime Error (the code compiles successfully)

**Answers:
c. Compilation Error**
2.what is output?
```java
class Question (

int i;

public Question (int i) {

this.ii--;

}

}

class Questionl extends Question {

public Questionl (int i) {

super (++i);

System.out.println(i);

}

nt

}

public class Check {

public static void main(String[] args) {

Questionl n = new Questionl (20);

}

}
```
 a. 20
 
 b. 21
 
 c. 19
 
 d. 22

**Answers:
b. 21**

3.what is output?
```java
class Question {

static int x;

static { x++;

}

{ ++x;

}

}

class Questionl extends Question (

static {

--x;

}

{ x--;

}

کھا

}

public class Check (

public static void main(String[] args) {

System.out.println(new Questionl().x);

}}
```





























