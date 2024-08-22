### pattern syntax checker
##### [https://www.hackerrank.com/contests/java-test3-1724254063/challenges/pattern-syntax-checker/submissions/code/1381666488]
```java
import java.util.Scanner;
import java.util.regex.*;

public class Solution
{
	public static void main(String[] args){
		Scanner in = new Scanner(System.in);
		int testCases = Integer.parseInt(in.nextLine());
		while(testCases>0){
			String pattern = in.nextLine();
          	//Write your code
            try{
                Pattern.compile(pattern);
                System.out.println("Valid");
            }
            catch(PatternSyntaxException e){
                System.out.println("Invalid");
            }
            testCases--;
		}
        in.close();
	}
}
```
### Java Primality Test
##### [https://www.hackerrank.com/contests/java-test3-1724254063/challenges/java-primality-test/submissions/code/1381666978]

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

        String n = bufferedReader.readLine();
        BigInteger bigInteger=new BigInteger(n);
       
        if(bigInteger.isProbablePrime(1)){
            System.out.println("prime");
        }
        else{
            System.out.println("not prime");
        }

        bufferedReader.close();
    }
}
```
### Java BigInteger
##### [https://www.hackerrank.com/contests/java-test3-1724254063/challenges/java-biginteger/submissions/code/1381667392]
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader=new BufferedReader(new InputStreamReader(System.in));
        String a=bufferedReader.readLine();
        String b=bufferedReader.readLine();
        BigInteger a1=new BigInteger(a);
        BigInteger a2=new BigInteger(b);
        BigInteger sum=a1.add(a2);
        BigInteger product=a1.multiply(a2);
        System.out.println(sum);
        System.out.println(product);
    }
}
```
