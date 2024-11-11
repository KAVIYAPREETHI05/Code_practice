### Arrays-DS
##### [https://www.hackerrank.com/challenges/arrays-ds/problem?isFullScreen=true]

```java
import java.util.*;


class Result {

    public static List<Integer> reverseArray(List<Integer> a) {
    // Write your code here
    int n=a.size();
    for(int i=0;i<n/2;i++){
        int temp=a.get(i);
        a.set(i,a.get(n-i-1));
        a.set(n-i-1,temp);
    }
return a;
    }

}

public class Solution {
    public static void main(String[] args)  {
        

        Scanner scan=new Scanner(System.in);
        int len=scan.nextInt();
        List <Integer>arr=new ArrayList<>();
        for(int i=0;i<len;i++){
            arr.add(scan.nextInt());
        }
        
        List <Integer>reversedArray=Result.reverseArray(arr);
        for(int i=0;i<len;i++){
            System.out.print(reversedArray.get(i)+" ");
        }

       
    }
}
```
