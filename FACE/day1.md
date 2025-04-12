https://www.hackerrank.com/contests/bannari-amman-training-coding-questions/challenges


### GCD

```java
//recursion
import java.io.*;
import java.util.*;

public class Solution {
    static int GCD(int a,int b){
       if(a==0){
           return b;
       }
        return GCD(b%a,a);
    }
/*
 static int GCD(int a,int b){
        while(b!=0){
            int temp=b;
            b=a%b;
            a=temp;
        }
        return a;
    }
*/
    static int findGCD(int n,int[] arr){
        int result=arr[0];
        
        for(int i=1;i<n;i++){
            result=GCD(result,arr[i]);
        }
        return result;
        
    }

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner s=new Scanner(System.in);
        int n=s.nextInt();
        int[] arr=new int[n];
        for(int i=0;i<n;i++){
            arr[i]=s.nextInt();
        }
        System.out.print(findGCD(n,arr));
    }
}
```

### TRAILING ZERO

```java
import java.io.*;
import java.util.*;

public class Solution {
   

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner s=new Scanner(System.in);
        int n=s.nextInt();
        long count=0;
        while(n>=5){
            count+=n/5;  
            n=n/5;
        }
       
        System.out.print(count);
    }
}
```

### VALID PALINDROME

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner st=new Scanner(System.in);
        String s=st.nextLine();
        
        StringBuilder sb=new StringBuilder();
        
        for(int i=0;i<s.length();i++){
            if(Character.isLetterOrDigit(s.charAt(i))){
                sb.append(Character.toLowerCase(s.charAt(i)));
            }
        }
        boolean check=true;
        int n=sb.length();
        int l=0;int r=n-1;
        
        while(l<r){
            if(sb.charAt(l)!=sb.charAt(r)){
                check=false;
                System.out.print(check);
                break;
            }
            l++;
            r--;
        }
        
       if(check){
           System.out.print(true);
       }
    }
}
```

```java
// without using string builder
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner st=new Scanner(System.in);
        String s=st.nextLine().toLowerCase();
        
        boolean check=true;
        int n=s.length();
        int l=0;int r=n-1;
        
        while(l<r){
            while(!Character.isLetterOrDigit(s.charAt(l)) && l<r){
                l++;
            }
            while(!Character.isLetterOrDigit(s.charAt(r)) && l<r){
                r--;
            }
            if(s.charAt(l)!=s.charAt(r)){
                check=false;
                System.out.print(check);
                break;
            }
            l++;
            r--;
        }
        
       if(check){
           System.out.print(true);
       }
    }
}
```

### Count of Perfect Squares in a Range

```java
// hint: It is known from number theory that only perfect squares have an odd number of factors.
import java.io.*;
import java.util.*;

public class Solution {
    static int countFactor(int n){
        int count=0;
        for(int i=1;i<=n;i++){
            if(n%i==0){
                count++;
            }
        }
        return count;
    }
    static boolean isperfect(int n){
        int count=countFactor(n);
        if(count%2==0){
            return false;
        }
      return true;
        
    }

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner s=new Scanner(System.in);
        int l=s.nextInt();
        int r=s.nextInt();
        int count=0;
        
        for(int i=l;i<=r;i++){
            if(isperfect(i)){
                count++;
            }
        }
        System.out.print(count);
    }
}
```

### Reverse Characters of Each Word in a Sentence 1

```java
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        String str = s.nextLine();
        
        StringBuilder sb = new StringBuilder(str);
        int n = sb.length();
        int start = 0;

        for (int end = 0; end <= n; end++) {
            if (end == n || sb.charAt(end) == ' ') {
                reverse(sb, start, end - 1);
                start = end + 1;
            }
        }

        System.out.print(sb.toString());
    }

    static void reverse(StringBuilder sb, int start, int end) {
        while (start < end) {
            char temp = sb.charAt(start);
            sb.setCharAt(start, sb.charAt(end));
            sb.setCharAt(end, temp);
            start++;
            end--;
        }
    }
}
```
