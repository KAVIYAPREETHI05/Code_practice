```java

import java.util.Scanner;
import java.util.HashSet;

public class lucky{
    static boolean findlucky(int n){
        String str=String.valueOf(n);
        HashSet <Character>hs=new HashSet<>();

        for(int i=0;i<str.length();i++){
            char ch=str.charAt(i);
            if(hs.contains(ch)){
                return false;
            }
            hs.add(ch);
           
        }
        return true;
    }
    
    public static void main(String[] args){
        Scanner s=new Scanner(System.in);
        int n=s.nextInt();
        System.out.print(findlucky(n));
    }
}
```
