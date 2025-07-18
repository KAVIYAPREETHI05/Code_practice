```java
import java.util.Scanner;

public class lcm{
    static int gcd(int a,int b){
        if(b==0){
            return a;
        }
        return gcd(b,a%b);
    }
    static int findLCM(int n,int[]arr){
        int maxlcm=-1;

        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                maxlcm=Math.max(maxlcm,(arr[i]*arr[j])/gcd(arr[i],arr[j]));

            }
        }
        return maxlcm;

    }
    public static void main(String[] args){
        Scanner s=new Scanner(System.in);
        int n=s.nextInt();

        int arr[]=new int[n];

        for(int i=0;i<n;i++){
            arr[i]=s.nextInt();
        }

        System.out.print(findLCM(n,arr));
    }
}
```
