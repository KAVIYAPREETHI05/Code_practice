```java
import java.util.Scanner;
public class addUnique {
    public static void main(String[] args){
        Scanner s=new Scanner(System.in);
        int n=s.nextInt();

        int[] arr=new int[n];
        for(int i=0;i<n;i++){
            arr[i]=s.nextInt();
        }

        int sum=0;
        for(int i=0;i<n;i++){
            int curr=arr[i];int flag=0;

           if(curr!=0){
            for(int j=i+1;j<n;j++){
                if(arr[i]==arr[j]){
                    arr[j]=0;
                    flag=1;
                }

            }
            if(flag==0){
                sum+=curr;
            }
           }


        }
        System.out.print(sum);
    }
    
}

```
