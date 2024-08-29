### Java Stdin and Stdout I
```java
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        int b=scan.nextInt();
        int c=scan.nextInt();
        
     

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        scan.close();
    }
}

```
### Java Stdin and Stdout II
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = scan.nextInt();
        double d=scan.nextDouble();
        scan.nextLine();
        String s=scan.nextLine();
        

        // Write your code here.

        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
        scan.close();
    }
}
```
### Java Output Formatting
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
            Scanner sc=new Scanner(System.in);
            System.out.println("================================");
            for(int i=0;i<3;i++){
                String s1=sc.next();
                int x=sc.nextInt();
                System.out.printf("%-15s%03d",s1,x);
                System.out.println("");
            }
            System.out.println("================================");
sc.close();
    }
}

```
```
    ================================

    java           100 

    cpp            065 

    python         050 

    ================================

```
### java loop1
```java
import java.io.*;
import java.util.*;
public class Solution {
    public static void main(String[] args) {
       Scanner scan=new Scanner(System.in);
       int n=scan.nextInt();
       for(int i=1;i<=10;i++){
           System.out.println(n + " x " + i + " = "+ n*i);
       }
       
        scan.close();
    }
}
```
###
