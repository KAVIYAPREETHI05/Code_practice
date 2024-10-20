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
 a. 1
 
 b. 2
 
 c. 0
 
 d. Compilation Error

**Answers:
c. 0**

4.Which exception is thrown when an array element is accessed beyond the array size?
 
 a. ArrayElementOutOfBounds
 
 b. ArrayIndexOutOfBoundsException
 
 c. ArrayIndexOutOfBounds
 
 d. None of these

**Answers:
b. ArrayIndexOutOfBoundsException**

5.what is output?
```java
class Q {

public void disp() { System.out.println("java");

}

}

class P extends Q {

public void disp() { System.out.println("nptel");

}

}

class C extends P {

public void disp() { super.super.disp(); System.out.println("course");

}

}

public class Question {

public static void main(String[] args) {

Cc = new C();

c.disp();

}
}
```
 a. java
 
 b. java
        course
 
 c. nptel
         course
 
 d. Compilation Error

Answers:
d. Compilation Error

6.Fill in the blank in the program so that the output is “Java”.
```java
interface X {

void display();

}

class Y implements X {

display() { System.out.println("Java");

}

//MISSING_CODE

}

public class MainClass {

public static void main(String[] args) {

Y r = new Y();

r.display();

}
}
```
 a. public void
 
 b. void
 
 c. private void
 
 d. static void

**Answers:
a. public void**

7.How many times will “Java” be printed if the following code is executed?
```java
class X {

static {

Y.display();

}

}

class Y extends X {

static void display() { System.out.println("Java");

}

}

public class MainClass {

public static void main(String[] args) { Y.display();

}

}
```
 a. 0
 
 b. 1
 
 c. 2
 
 d. 3

**Answers:
c. 2**

8.The following is a simple program using the concept of thread. What is the output of the following program?
```java
public class Question extends Thread {

public void run() {

for (int i = 1; i < 8; i++) {

System.out.print(++i + " ");

}

}

public static void main(String args[]) { Question t1 = new Question();

t1.run();

}

}
```
 a. 1 3 5 7
 
 b. 2 4 6 8
 
 c. 1 3 5 7 9
 
 d. 2 4 6

**Answers:
b. 2 4 6 8**

9.For the program given below, what will be the output after its execution?
```java
public class Main {

public static void main(String[] args) {

Thread thread = Thread.currentThread(); thread.run();

System.out.print(Thread.activeCount());

}

}
```
 a. 1
 
 b. 2
 
 c. 0
 
 d. 01

**Answers:
a. 1**

10.Which of the following method returns a reference to the currently executing thread object?
 
 a. public static boolean interrupted();
 
 b. public static Thread currentThread();
 
 c. public final boolean isAlive();
 
 d. public final void suspend();

**Answers:
b. public static Thread currentThread();**

# WEEK-7

1.Which of these exception is thrown in cases when the file specified for writing is not found?
 
 a. IOException
 
 b. FileException
 
 c. FileNotFoundException
 
 d. FileInputException

**Answers:
c. FileNotFoundException**

2.Which of these values is returned by read() method is end of file (EOF) is encountered?
 
 a. 0
 
 b. 1
 
 c. -1
 
 d. Null

**Answers:
c. -1**

3.what is output?
```java
import java.io.*;

class Chararrayinput {

public static void main(String[] args) {

String obj = "abcdef";

int length = obj.length();

char c[] = new char[length];

obj.getChars(0, length, c, 0);

CharArray Reader input1 = new CharArrayReader (c);

CharArray Reader input2 = new CharArrayReader (c, 0, 3);

int i;

try {

while ((1 = input2.read()) != -1) { System.out.print((char) i);

}

} catch (IOException e) {

e.printStackTrace();

}

}
```
 a. abc
 
 b. abcd
 
 c. abcde
 
 d. abcdef

**Answers:
a. abc**

4.What is the purpose of a ByteArrayOutputStream in Java?
 
 a. To write binary data to an output stream
 
 b. To read binary data from an input stream
 
 c. To convert characters to bytes
 
 d. To store binary data in memory

**Answers:
d. To store binary data in memory**

5.Which method is used to read b length bytes from the input stream into an array?
 
 a. public void read(int b)throws IOException{{
 
 b. public int read(byte[ ] b)throws IOException{}
 
 c. public void read(byte[ ] b)throws IOException{}
 
 d. public int read(int b)throws IOException{}

**Answers:
b. public int read(byte[ ] b)throws IOException{}**

6.Which method is used to create a directory with fileattributes?
 
 a. Path.create()
 
 b. Path.createDirectory()
 
 c. Files.createDirectory(path, fileAttributes)
 
 d. Files.create(fileAttributes)

**Answers:
c. Files.createDirectory(path, fileAttributes)**

7. what is output?
```java
public class Calculator { int num = 100;

public void calc(int num) { this.num = num 10; }

public void printNum() { System.out.println(num);

}

public static void main(String[] args) {

Calculator obj = new Calculator();

obj.calc(2);

obj.printNum();

}

}
```
 a. 20
 
 b. 100
 
 c. 1000
 
 d. 2

**Answers:
a. 20**

8.Which class is used to write primitive data types to an output stream in Java?
 
 a. DataOutputStream
 
 b. ObjectOutputStream
 
 c. OutputStream
 
 d. PrintWriter

**Answers:
a. DataOutputStream**

9.what is output?
```java
import java.io.*;

public class W7 {

public static void main(String[] args) {

try {

PrintWriter writer = new PrintWriter(System.out);

writer.write(9 + 97);

writer.close();

} catch (Exception e) { System.out.println(e);

}

}

}
```
 
 a. It will give compile-time error
 
 b. It will give run-time error
 
 c. j
 
 d. 106

**Answers:
c. j**

10.what is output?
```java
import java.io.File;

class FileSizeEample {

public static void main(String[] args) { // Specify the file path String filePath = "file.txt";

// Create a File object File file = new File(filePath);

// Get the size of the file long fileSize = file.length();

// Print the size of the file System.out.println(fileSize);

}

}
```
 a. 42
 
 b. 35
 
 c. 7
 
 d. 0

**Answers:
a. 42**

# WEEK-8

1.What does AWT stand for in Java?
 
 a. Applet Windowing Toolkit
 
 b. Abstract Window Toolkit
 
 c. Absolute Windowing Toolkit
 
 d. Amazing Window Toolkit

**Answers:
b. Abstract Window Toolkit**

2.In Java, what is the purpose of a Card Layout?
 
 a. To create a card game interface
 
 b. To arrange components in a card-like fashion
 
 c. To manage multiple panels within a single container
 
 d. To display images of cards

**Answers:
c. To manage multiple panels within a single container**

3.Which layout manager divides the container into five regions: North, South, East, West, and Center?
 
 a. Border Layout
 
 b. Grid Layout
 
 c. Flow Layout
 
 d. Card Layout

**Answers:
a. Border Layout**

4.In Java, what is the primary purpose of a layout manager?
 
 a. To manage memory allocation
 
 b. To arrange GUI components within a container
 
 c. To handle exception handling
 
 d. To control database connections

**Answers:
b. To arrange GUI components within a container**

5.what is output?
```java
import java.awt.*;

import java.awt.event.*;

public class ButtonExample extends Frame {

public static void main(String[] args) {

Button Example frame = new ButtonExample();

Button b = new Button("Programming in Java - 2024");

b.setBounds (30, 50, 80, 30);

frame.add(b);

frame.setSize (300, 200);

frame.setLayout (null);

frame.setVisible(true);

}

}
```
 
 a. Compilation error
 
 b. An empty frame with no button
 
 c. A frame with a button "Programming in Java - 2024" at coordinates (30, 50)
 
**Answers:
c. A frame with a button "Programming in Java - 2024" at coordinates (30, 50)**

6.Which layout manager arranges components in a top-to-bottom flow, adding them to the next available position?
 
 a. Grid Layout
 
 b. Flow Layout
 
 c. Border Layout
 
 d. Card Layout

**Answers:
b. Flow Layout**

7.What is the significance of AWT components being heavyweight?
 
 a. They have higher memory requirements
 
 b. They are slower in performance
 
 c. They are dependent on the underlying operating system
 
 d. They are easier to customize

**Answers:
c. They are dependent on the underlying operating system**

8.Which AWT concept allows you to handle events such as button clicks or mouse movements?
 
 a. Event Handling
 
 b. Function Overloading
 
 c. Mouse Manager
 
 d. GUI Processing

**Answers:
a. Event Handling**

9.Which layout manager organizes components in a grid, with each cell of the grid containing a component?
 
 a. Flow Layout
 
 b. Grid Layout
 
 c. Border Layout
 
 d. Card Layout

**Answers:
b. Grid Layout**

10.what is output?
```java
import java.awt.*;

public class LayoutExample extends Frame ( public static void main(String[] args) { Layout Example frame = new LayoutExample(); Button b1 = new Button("Button 1"); Button b2 = new Button("Button 2"); Button b3 = new Button("Button 3");

frame.add(b1);

frame.add(b2);

frame.add(b3);

// create a flow layout

frame.setLayout(new FlowLayout()); frame.setLayout (new GridLayout (2, 2));

frame.setSize(300, 200);

frame.setVisible(true);

}
}
```
 
 a. Grid Layout
 
 b. Border Layout
 
 c. Flow Layout
 
 d. Card Layout

**Answers:
a. Grid Layout**

# WEEK-9

1.Which of the following is a one-line input field that allows the user to choose a number or an object value from an ordered sequence?
 
 a. Jtextarea
 
 b. Jtextfield
 
 c. Jspinner
 
 d. Jslider

**Answers:
c. Jspinner**
2. what is output?
 
 a. Both “OK” and “Cancel” button is added, but only “Cancel” button is visble.
 
 b. Only “OK” button is added and visible, “Cancel” button is not added.
 
 c. Only “Cancel” button will be added and visible, “OK” button is not added.
 
 d. Code throws an ERROR.

**Answers:
a. Both “OK” and “Cancel” button is added, but only “Cancel” button is visble.**

3.Which of the following is a container for other components and is used to build bespoke panels for organizing and arranging components?
 
 a. Jpanel
 
 b. Jframe
 
 c. Jcombo
 
 d. JBox
**Answers:
a. Jpanel**

4.Which of the following component gives a drop-down list of options from which to choose?
 
 a. Jpanel
 
 b. Jbutton
 
 c. JComboBox
 
 d. Jbox

**Answers:
c. JComboBox**

5.Which of the following Swing components inherently support the WindowListener interface?
 
 a. Swing frames (JFrame)
 
 b. Swing checkboxes (JCheckBox)
 
 c. None of these
 
 d. Swing combo boxes (JComboBox)

**Answers:
a. Swing frames (JFrame)**

6.Which class in Swing provides a graphical way to display images, icons, or custom graphics?
 
 a. Jimage
 
 b. Jlabel
 
 c. JImageIcon
 
 d. JDialog

**Answers:
b. Jlabel**

7.What is/are the way(s) to create a Frame in Java Swing?
 
 a. By creating the object of Frame class (association)
 
 b. None of these
 
 c. By importing a package named Jframe
 
 d. By declaring a class with name JFrame

**Answers:
a. By creating the object of Frame class (association)**

8.Which method is used to set the graphics current color to the specified color in the graphics class?
 
 a. public abstract void setFont(Font font)
 
 b. public abstract void setColor(Color c)
 
 c. public abstract void drawString(String str, int x, int y)
 
 d. None of the above

**Answers:
b. public abstract void setColor(Color c)**

9.When are the keyboard events fired?
 
 a. When the user manually calls the button
 
 b. When the user right clicks the mouse
 
 c. When the user calls the modifier
 
 d. When the user clicks a key

**Answers:
d. When the user clicks a key**

10.Which of the following function is used to specify the layout of a container.
 
 a. UseLayeout()
 
 b. setLayout()
 
 c. layout()
 
 d. DesignLayout()

**Answers:
b. setLayout()**

# WEEK-10

1.what is output?
```java
import java.net.*;

public class NPTEL {

public static void main(String[] args) {

try {

URI uri = new URI("https://nptel.ac.in/");

URL url = uri.toURL();

System.out.println("Protocol:

+ url.getProtocol());

System.out.println("Host Name: " + url.getHost());

System.out.println("Port Number: + url.getPort());

} catch (Exception e) {

System.out.println(e);

}

}

}
```
 
 a. Protocol: https
 
 b. Host Name: nptel.ac.in
 
 c. Port Number: -1
 
 d. All of the mentioned

**Answers:
d. All of the mentioned**

2.What will be the output of the following Java program?
```java
import java.net.*;

class NPTEL {

public static void main(String[] args) throws UnknownHostException ( InetAddress obj = InetAddress.getByName("nptel.ac.in"); System.out.print(obj1.getHostName());

}

}
```
 
 a. nptel
 
 b. nptel.ac.in
 
 c. www.nptel.ac.in
 
 d. none of the mentioned

Answers:
b. nptel.ac.in

3.Which class provides methods to work with URLs?

 a. URLConnection

 b. HttpURL
 
 c. NetURL
 
 d. URL

**Answers:
d. URL**

4.Which exception is thrown when a connection cannot be established with a remote server?
 
 a. IOException
 
 b. UnknownHostException
 
 c. ConnectionException
 
 d. NetworkException

**Answers:
b. UnknownHostException**

5.Which class provides methods to create a client-side socket in Java?
 
 a. ServerSocket
 
 b. NetSocket
 
 c. Socket
 
 d. ClientSocket

**Answers:
c. Socket**

6.Which of the following statement is TRUE?
 
 a. With stream sockets there is no need to establish any connection and data flows between the processes are as continuous streams.
 
 b. Stream sockets are said to provide a connection-less service and UDP protocol is used
 
 c. Datagram sockets are said to provide a connection-oriented service and TCP protocol is used
 
 d. With datagram sockets there is no need to establish any connection and data flows between the processes are as packets.

**Answers:
d. With datagram sockets there is no need to establish any connection and data flows between the processes are as packets.**

7.The server listens for a connection request from a client using which of the following statement?
 
 a. Socket s = new Socket(ServerName, port);
 
 b. Socket s = serverSocket.accept()
 
 c. Socket s = serverSocket.getSocket()
 
 d. Socket s = new Socket(ServerName);

**Answers:
b. Socket s = serverSocket.accept()**

8.Which of the following is/are application layer protocol(s)?
 
 a. TCP
 
 b. UDP
 
 c. ARP
 
 d. SMTP

**Answers:
d. SMTP**

9.In the following URL, identify the Resource name?

https://nptel.ac.in
 
 a. https
 
 b. nptel.ac.in
 
 c. ac.in
 
 d. nptel

**Answers:
b. nptel.ac.in**

10.what is output?
```java
import java.net.*;

public class NPTEL {

public static void main(String[] args) {

try {

InetAddress address = InetAddress.getByName("nptel.ac.in"); System.out.println("Host Name: + address.getHostName());

System.out.println("IP Address: "+ address.getHostAddress

} catch (Exception e) { System.out.println(e);

}

}
}
```
 
 a. Just prints the IP address of the local machine
 
 b. Prints the IP address and host name of the local machine
 
 c. Prints the IP address and host name of "nptel.ac.in"
 
 d. Just prints the IP address of "nptel.ac.in"

**Answers:
c. Prints the IP address and host name of "nptel.ac.in"**

# WEEK-11

1.How do you establish a connection to a database using JDBC?
 
 a. By creating an instance of the Connection interface
 
 b. By using the DriverManager.getConnection() method
 
 c. By implementing the Connection interface
 
 d. By extending the Connection class

**Answers:
b. By using the DriverManager.getConnection() method**

2.Which method executes a simple query and returns a single Result Set object?
 
 a. executeQuery()
 
 b. executeUpdate()
 
 c. execute()
 
 d. run()

**Answers:
a. executeQuery()**

3.What is the correct order to close database resources?
 
 a. Connection then Statement then ResultSet
 
 b. ResultSet then Statement then Connection
 
 c. Statement then Connection then ResultSet
 
 d. Statement then ResultSet then Connection

**Answers:
b. ResultSet then Statement then Connection**

4.Which of the following ensures that the correct driver is used to access each data source.
 
 a. java.sql.Connection
 
 b. java.sql.DriverManager
 
 c. java.sql.Statement
 
 d. java.sql.Driver

**Answers:
b. java.sql.DriverManager**

5.What is the purpose of the ResultSet interface in JDBC?
 
 a. To store the result of a query
 
 b. To execute SQL queries
 
 c. To manage database connections
 
 d. To update data in the database

**Answers:
a. To store the result of a query**

6.The following is a statement in Java using JDBC.
```java
Connection con = DriverManager.getConnection( "jdbc:mysql://localhost:3306/nptel","joy","java" );
```
Which of the following statement is FALSE?
 
 a. 3306 is the default MySQL port.
 
 b. Database name is ‘nptel’
 
 c. The database server is hosted on IP 127.0.0.1
 
 d. Password for ‘java’ user is ‘joy’

**Answers:
d. Password for ‘java’ user is ‘joy’**

7.Which resources have their close() method called when this code runs?

```java
public static void runquery (Connection conn) throws SQLException {

try (Statement stmt = conn.createStatement()) { ResultSet rs = stmt.executeQuery("select * from clowns"); rs.next();

}

}
```

 a. No close() methods are called
 
 b. Only Statement
 
 c. Only Statement and Connection
 
 d. Only Statement and ResultSet

**Answers:
d. Only Statement and ResultSet**

8.Which of the following is used to call stored procedure?
 
 a. Statement
 
 b. PreparedStatement
 
 c. CallableStatment
 
 d. CalledStatement

**Answers:
c. CallableStatment**

9.The executeUpdate method can be used with
 
 a. Statements(Select and Update both)
 
 b. Select statement.
 
 c. Update/delete/insert operations in the database.
 
 d. Only insert operation.

**Answers:
c. Update/delete/insert operations in the database.**

10.What does setAutoCommit(false) do?
 
 a. commits transaction after each query
 
 b. explicitly commits transaction
 
 c. does not commit transaction automatically after each query
 
 d. never commits transaction

**Answers:
c. does not commit transaction automatically after each query**

# WWEK-12

1.Execution of the following SQL command

 SELECT FROM myTable
 
 using JDBC program will return a ResultSet object. This object is:

 a. Same as the myTable.
 
 b. All records in verbatim from the table.
 
 c. All records in verbatim from the table but those records with null values.
 
 d. All records in verbatim from the table but those records are not with null values.

**Answers:
b. All records in verbatim from the table.**

2.Which of the following method is used to set a frame, f with size 300 × 200 pixels?

JFrame f=newJFrame();

 a. f.setSize(300, 200)
 
 b. f.setSize(200, 300)
 
 c. f.paint(300, 200)
 
 d. f.setVisible(300, 200)

**Answers:
a. f.setSize(300, 200)**

3.Consider the following program:
```java
public class Question {

public static void main(String[] args) {

String str = "NPTEL Programming in JAVA - JULY 2024";

System.out.println(str.length());

}

}
```
 a. 38
 
 b. 39
 
 c. 40
 
 d. 41

**Answers:
b. 39**

4.What is the output of the following program?
```java
public class Test {

public static void aMethod() throws Exception {

try {

throw new Exception();

} finally {

System.out.print("finally ");

}

}

public static void main(String args[]) {

try {

aMethod();

} catch (Exception e) {

System.out.print("exception ");

}

System.out.print("finished ");

}

}
```
 a. finally
 
 b. exception finished
 
 c. finally exception finished
 
 d. Compilation fails

**Answers:
c. finally exception finished**

5.What is the output of the following program?
```java
class Program {

public static void main(String[] args) { int counter = 10;

do { System.out.print(2 / counter); counter--;

} while (counter > 2);

}

}
```
 a. 00000012
 
 b. 00000000
 
 c. 10011001
 
 d. 12211221

**Answers:
b. 00000000**

6.What should be the value of X and Y for the output of the below program to be 36?
```java
public class Question {

public static void main(String[] args) {

int x = 4 ;

int x = 5 ;

int sum = 0;

for (int i = 0 ; i < X; i++) {

for (int j = i; j < Y; j++) { sum = sum + j;

} } System.out.print(sum);

}
}
```
 a. X = 6 and Y = 5
 
 b. X = 2 and Y = 7
 
 c. X = 1 and Y = 10
 
 d. X = 4 and Y = 5

**Answers:
d. X = 4 and Y = 5**

7.Which of the following options correctly initializes the elements of the numbers array with values 1, 2, 3, 4, and 5?

```java
public class NPTEL {

public static void main(String[] args) {

int[] numbers = new int[5];

// #1: Missing code block

System.out.println("First element: + numbers[0]);

}

}
```
a. numbers = {1, 2, 3, 4, 5};

b. for (int i = 1; i < numbers.length; i++) { numbers[i] = i; }

c. numbers[] = {1, 2, 3, 4, 5};

d. numbers = new int[]{1, 2, 3, 4, 5};

**Answers:
d. numbers = new int[]{1, 2, 3, 4, 5};**

8) Which of the following statements are correct and would NOT cause a compilation error?

 ```java
I.float[] = new float(3);

II. float f1 [] = new float[];

III.float[] f2 = new float[3];

IV. float f3 [] = new float[3];

V. float f4 [] = { 1.0f, 2.0f, 2.0f };

vi. float f5 [] = new float() { 1.0f, 2.0f, 3.0f);
```
 a. iii, iv, v, vi
 
 b. i, ii, iii, iv
 
 c. ii, iii, v, vi
 
 d. i, ii, iv, vi

**Answers:
a. iii, iv, v, vi**

9.What will be the output of this program?
```java
public class NPTEL {

public static void main(String[] args) {

String strl = "Hello";

String str2 = "Hello";

String str3 = new String("Hello");

System.out.print((str1 == str2) + ");

System.out.print(str1 = str3);

}

}
```
 
 a. true false
 
 b. false true
 
 c. true true
 
 d. false false

**Answers:
a. true false**

10.What will be the output of this program?

```java
public class NPTEL {

public static void main(String[] args) {

try {

int num = 10 / 0;

System.out.println(num);

} catch (ArithmeticException e) {

System.out.println("Arithmetic exception occurred");

} finally {

System.out.println("Finally block executed");

}

}

}
```
 a. Compilation ERROR
 
 b. “Finally block executed”
 
 c. “Arithmetic exception occurred Finally block executed”
 
 d. Runtime ERROR

**Answers:
c. “Arithmetic exception occurred Finally block executed”**
























