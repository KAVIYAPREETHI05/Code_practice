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
