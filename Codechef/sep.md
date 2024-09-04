## Day-1
### Clear Day
```cpp
#include <stdio.h>

int main(void) {
    int n,Y,z;
    scanf("%d %d",&n,&Y);
    
    z=7-n-Y;
    printf("%d",z);
	// your code goes here

}
```
## Day-2
### Search an element in an array
```java
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		Scanner scan=new Scanner(System.in);
		int n=scan.nextInt();
		int target=scan.nextInt();
		int arr[]=new int[n];
		for(int i=0;i<n;i++){
		    arr[i]=scan.nextInt();
		}
		int found=0;
		for(int i=0;i<n;i++){
		    if(arr[i]==target){
		        found=1;
		        System.out.println("YES");
		        break;
		    }
		    
		}
		if(found==0){
		    System.out.println("NO");
		}
		

	}
}
//https://www.codechef.com/practice/course/arrays/ARRAYS/problems/SEARCHINARR
```
## Day-3
### Find maximum in an Array
```java
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		Scanner scan=new Scanner(System.in);
		int T=scan.nextInt();
		
		while(T>0){
		    int n=scan.nextInt();
		    int a[]=new int[n];
		    for(int i=0;i<n;i++){
		        a[i]=scan.nextInt();
		        
		    }
		    int max=a[0];
		    for(int i=0;i<n;i++){
		        if(a[i]>max){
		            max=a[i];
		        }
		        
		    }
		    System.out.println(max);
		    T--;
		}

	}
}

```
## Day-4
### Take discount or Not
```java
import java.util.Scanner;



public class Main {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);



        // Read the number of test cases

        int t = scanner.nextInt();



        // Process each test case

        while (t-- > 0) {

            int N = scanner.nextInt();  // Number of items

            int X = scanner.nextInt();  // Cost of the coupon

            int Y = scanner.nextInt();  // Discount amount

            

            int[] prices = new int[N];

            

            // Read item prices

            for (int i = 0; i < N; i++) {

                prices[i] = scanner.nextInt();

            }



            // Calculate the total cost without the coupon

            int totalWithoutCoupon = 0;

            for (int price : prices) {

                totalWithoutCoupon += price;

            }



            // Calculate the total cost with the coupon

            int totalWithCoupon = X;  // Initial cost is the coupon price

            for (int price : prices) {

                if (price > Y) {

                    totalWithCoupon += (price - Y);

                }

                // If price <= Y, the item becomes free, so no need to add anything

            }



            // Determine if Chef should buy the coupon

            if (totalWithCoupon < totalWithoutCoupon) {

                System.out.println("COUPON");

            } else {

                System.out.println("NO COUPON");

            }

        }



        scanner.close();  // Close the scanner

    }

}


```
