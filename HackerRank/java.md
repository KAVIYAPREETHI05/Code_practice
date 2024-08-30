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
### Java Loops II
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        int q=scan.nextInt();
        for(int i=0;i<q;i++){
            int a=scan.nextInt();
            int b=scan.nextInt();
            int n=scan.nextInt();
            int curr=a;
            for(int j=0;j<n;j++){
                curr+=(Math.pow(2,j))*b;
                System.out.print(curr+" ");
            }
            System.out.println("");
        }
        
        
        
    }
}
```
### Java Datatypes
```java
import java.io.*;
import java.util.*;
import java.math.BigInteger;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int T = scan.nextInt();
        while (T-- > 0) {
            String input = scan.next(); 
            try {
           
                long n = Long.parseLong(input);
                System.out.println(n + " can be fitted in:");
                if (n>=(Short.MIN_VALUE)&& n<=(Short.MAX_VALUE)) {
                    System.out.println("* short");
                }
                if (n>=(Integer.MIN_VALUE)&& n<=(Integer.MAX_VALUE)) {
                    System.out.println("* int");
                }
                if (n>=(Long.MIN_VALUE)&& n<=(Long.MAX_VALUE)) {
                    System.out.println("* long");
                }
                
            } catch (NumberFormatException e) {
                // Use the stored input directly, no need to call scan.next() again
                System.out.println(input + " can't be fitted anywhere.");
            }
        }
        scan.close();
    }
}

```
### Java End-of-file
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
           int line=1;
        while(scan.hasNextLine()){
         
            String input=scan.nextLine();
            if(input.equals("EOF")){
                break;
            }
           
            System.out.println(line +" "+input);
            line++;
        }
        scan.close();
    }
}
```
### Java Static Initializer Block
```java
import java.io.*;
import java.util.*;

public class Solution {
    

    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        int B=scan.nextInt();
        int H=scan.nextInt();
        if(B<=0 || H<=0){
            System.out.println("java.lang.Exception: Breadth and height must be positive");
            
        }
        else{
            System.out.println(B*H);
        }
        
    }
}
```
### Java Int to String
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        int n=scan.nextInt();
        String s=Integer.toString(n);
        if(s.equals(Integer.toString(n))){
            System.out.println("Good job");
        }
        else{
            System.out.println("Wrong answer");
        }
    }
}
```
