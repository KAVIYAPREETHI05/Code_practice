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
###
