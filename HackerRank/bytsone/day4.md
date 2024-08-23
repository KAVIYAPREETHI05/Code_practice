### Java Stdin and Stdout I
##### [https://hackerrank.com/contests/test4-1724339183/challenges/java-stdin-and-stdout-1/submissions/code/1381703073]
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
    }
}
```

### java if else
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-if-else/submissions/code/1381703372]
```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {



    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");
        if(N%2!=0){
            System.out.println("Weird");
        }
        else{
            if(N>=2 && N<=5){
                System.out.println("Not Weird");
            }
            else if(N>=5 && N<=20){
                System.out.println("Weird");
            }
            else if(N>20){
                System.out.println("Not Weird");
            }
        }

        scanner.close();
    }
}

```
### Java Stdin and Stdout II
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-stdin-stdout/submissions/code/1381703662]
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = scan.nextInt();
        
        double d=scan.nextDouble();
        scan.nextLine();
        String s=scan.nextLine();
        

        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
    }
}
```
### Java Output Formatting
#### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-output-formatting/submissions/code/1381703990]
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
            Scanner sc=new Scanner(System.in);
            System.out.println("================================");
            for(int i=0;i<3;i++){
                String s1=sc.next();
                int x=sc.nextInt();
                System.out.printf("%-15s%03d%n",s1,x);
                
            }
            System.out.println("================================");

    }
}
```
### Java Loops I
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-loops-i/submissions/code/1381704274]
```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;



public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        int N = Integer.parseInt(bufferedReader.readLine().trim());
        for(int i=1;i<=10;i++){
            System.out.println(N +" x "+i+" = "+N*i);
        }

        bufferedReader.close();
    }
}
```
### Java Loops II
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-loops/submissions/code/1381704529]
```java
import java.util.*;
import java.io.*;

class Solution{
    public static void main(String []argh){
        Scanner in = new Scanner(System.in);
        int t=in.nextInt();
        for(int i=0;i<t;i++){
            int a = in.nextInt();
            int b = in.nextInt();
            int n = in.nextInt();
             int sum = a; // Initialize sum with a
            for (int j = 0; j < n; j++) {
                sum += (Math.pow(2, j) * b); // Calculate the current term in the series
                System.out.print(sum + " "); // Print the current term followed by a space
            }
            System.out.println(); // Move to the next line after each series
        
        }
        in.close();
    }
}
```
### data types
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-datatypes/submissions/code/1381704806]
```java
import java.util.*;
import java.io.*;



class Solution{
    public static void main(String []argh)
    {



        Scanner sc = new Scanner(System.in);
        int t=sc.nextInt();

        for(int i=0;i<t;i++)
        {

            try
            {
                long x=sc.nextLong();
                System.out.println(x+" can be fitted in:");
                if(x>=-128 && x<=127)System.out.println("* byte");
                 if(x >= -32768 && x <= 32767) {
                    System.out.println("* short");
                }
                if(x >= -2147483648L && x <= 2147483647L) {
                    System.out.println("* int");
                }
                if(x >= -9223372036854775808L && x <= 9223372036854775807L) {
                    System.out.println("* long");
            }
            }
            catch(Exception e)
            {
                System.out.println(sc.next()+" can't be fitted anywhere.");
            }

        
    }
}
}
```
### Java End-of-file
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-end-of-file/submissions/code/1381705092]
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        int lineno=1;
        while(scan.hasNextLine()){
            String line=scan.nextLine();
            System.out.println(lineno + " " + line);
            lineno++;
        }
        scan.close();
    }
}
```
### Java Static Initializer Block
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-static-initializer-block]
```java

    static boolean flag = true;
    static int B, H;

    static {
        Scanner scan = new Scanner(System.in);
        B = scan.nextInt();
        H = scan.nextInt();
        if (B <= 0 || H <= 0) {
            flag = false;
            System.out.println("java.lang.Exception: Breadth and height must be positive");
        }
    }
```
### Java Date and Time
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-date-and-time/submissions/code/1381706333]
```java
class Result {

    /*
     * Complete the 'findDay' function below.
     *
     * The function is expected to return a STRING.
     * The function accepts following parameters:
     *  1. INTEGER month
     *  2. INTEGER day
     *  3. INTEGER year
     */

    public static String findDay(int month, int day, int year) {
         Calendar calendar = new GregorianCalendar(year, month - 1, day);
        int dayOfWeek = calendar.get(Calendar.DAY_OF_WEEK);
        String[] daysOfWeek = {"SUNDAY", "MONDAY", "TUESDAY", "WEDNESDAY", "THURSDAY", "FRIDAY", "SATURDAY"};
        return daysOfWeek[dayOfWeek - 1];
    

    }

}
```
### Java Currency Formatter
##### [https://www.hackerrank.com/contests/test4-1724339183/challenges/java-currency-formatter]
```java
import java.util.*;
import java.text.*;

public class Solution {
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double payment = scanner.nextDouble();
        scanner.close();
        
        NumberFormat usFormat = NumberFormat.getCurrencyInstance(Locale.US);
        String us = usFormat.format(payment);
        
        // India formatting
        NumberFormat indiaFormat = NumberFormat.getCurrencyInstance(new Locale("en", "IN"));
        String india = indiaFormat.format(payment);
        
        // China formatting
        NumberFormat chinaFormat = NumberFormat.getCurrencyInstance(Locale.CHINA);
        String china = chinaFormat.format(payment);
        
        // France formatting
        NumberFormat franceFormat = NumberFormat.getCurrencyInstance(Locale.FRANCE);
        String france = franceFormat.format(payment);
        
        System.out.println("US: " + us);
        System.out.println("India: " + india);
        System.out.println("China: " + china);
        System.out.println("France: " + france);
    }
}
```
