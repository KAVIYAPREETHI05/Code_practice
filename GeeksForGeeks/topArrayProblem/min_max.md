### Min and Max in Array
##### [https://www.geeksforgeeks.org/problems/find-minimum-and-maximum-element-in-an-array4428/1]
## c
```c
struct pair getMinMax(long long int a[], long long int n) {
    struct pair result;
        result.max=a[0]; result.min=a[0];
        for(int i=1;i<n;i++){
            if(a[i]>result.max){
                result.max=a[i];
            }
            else if(a[i]<result.min){
                result.min=a[i];
            }
        }
        return result;
    }
```
## cpp
```cpp
class Solution {
public:
    pair<long long, long long> getMinMax(long long a[], int n) {
        // code here
            long long int  max=a[0]; long long int min=a[0];
        for(int i=1;i<n;i++){
            if(a[i]>max){
                max=a[i];
            }
            else if(a[i]<min){
                min=a[i];
            }
        }
        return {min,max};
}
};
```
## java
```java
class Solution 
{
    static Pair getMinMax(long a[], long n)  
    {
        //Write your code here
        long max=a[0];long min=a[0];
        for(int i=0;i<n;i++){
            if(a[i]>max){
                max=a[i];
            }
            else if(a[i]<min){
                min=a[i];
            }
        }
        return new Pair(min,max);
    }
    }
```
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
