## armstrong number
### c
```c
#include<stdio.h>
#include<math.h>

int main(){
    int n;
    scanf("%d",&n);
    int number=n;
    int count=0;
    while(n>0){
        count++;
        n=n/10;
    }
    n=number;int sum=0;
    while(n>0){
        int digit=n%10;
        int power=1;
        for(int i=0;i<count;i++){
            power*=digit;
        }
        sum+=power;
        n=n/10;
    }
    if(sum==number){
        printf("YES armstrong number");
    }
    else{
        printf("NO not an armstrong number");
    }
    
}
```
### java
```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        int n=scan.nextInt();
        int count=0;
        int number=n;
        while(n>0){
            count++;
            n/=10;
        }
        n=number; int sum=0;
        while(n>0){
            int digit=n%10;
            int power=1;
            for(int i=0;i<count;i++){
                power*=digit;
            }
            sum+=power;
            n/=10;
        }
        if(sum==number){
            System.out.println("YES armstrong number");
        }
        else{
            System.out.println("NO not an armstrong number");
        }
    }
}
```
