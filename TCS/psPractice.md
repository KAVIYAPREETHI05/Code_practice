## zero count

### c
```c

#include <stdio.h>
int zeroCount(int str_length,int max_ones){
     if(str_length==max_ones){
            return 0;
        }
        else if(str_length==0){
            return 0;
        }
        int max_zeros=0;
        if(str_length>0){
            max_zeros=1;
        }
        return max_zeros;
}

int main() {
    int str_length;
    scanf("%d",&str_length);
    int max_ones;
    scanf("%d",&max_ones);
    if(max_ones>str_length){
        printf("invalid");
    }
    
    printf("%d",zeroCount(str_length,max_ones));

    return 0;
}
```
### java
```java


import java.util.*;

class Main{
    public static int zeroCount(int str_length,int max_ones){
         if(str_length==max_ones){
            return 0;
        }
        else if(str_length==0){
            return 0;
        }
        int max_zeros=0;
        if(str_length>0){
            max_zeros=1;
        }
        return max_zeros;
        
    }
    public static void main(String [] args){
        Scanner scan=new Scanner(System.in);
        int str_length=scan.nextInt();
        int max_ones=scan.nextInt();
        
        System.out.println(zeroCount(str_length,max_ones));
        
       
       
        
    }
}

```
##  PrimeConstruction
### c
```c
#include <stdio.h>
#include<limits.h>

int main() {
    
 int n;
 scanf("%d",&n);
 int arr[n];
 for(int i=0;i<n;i++){
     scanf("%d",&arr[i]);
 }
       
        int min=INT_MAX;
        for(int i=0;i<n;i++){
            if(arr[i]<min){
                min=arr[i];
            }
        }
        int num=min+1;
        int found=1;
        while(1){
            found=1;
            for(int i=0;i<n;i++){
                
                if(arr[i]!=min){
                    if(num%arr[i]!=min){
                        
                        found=0;
                        break;
                    }
                }
            }
            if(found){
               printf("%d",num);
                break;
            }
            num++;
            
        }
    }

```


### java
```java
import java.util.*;

class Main{
    public static void main(String[] args){
        Scanner scan=new Scanner(System.in);
        int n=scan.nextInt();
        int [] arr=new int[n];
        
        for(int i=0;i<n;i++){
            arr[i]=scan.nextInt();
        }
        int min=Integer.MAX_VALUE;
        for(int i=0;i<n;i++){
            if(arr[i]<min){
                min=arr[i];
            }
        }
        int num=min+1;
        boolean found=false;
        while(!found){
            found=true;
            for(int i=0;i<n;i++){
                
                if(arr[i]!=min){
                    if(num%arr[i]!=min){
                        
                        found=false;
                        break;
                    }
                }
            }
            if(found){
                System.out.println(num);
                break;
            }
            num++;
            
        }
    }
}
```
