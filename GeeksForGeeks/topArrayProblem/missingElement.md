### Missing in Array
##### [https://www.geeksforgeeks.org/problems/missing-number-in-array1416/1]
## cpp
```cpp
class Solution {
  public:

    // Note that the size of the array is n-1
    int missingNumber(int n, vector<int>& arr) {
long long arrSum=0;
        for(int i=0;i<n-1;i++){
            arrSum+=arr[i];
        }
long long OrigSum=(n*(n+1))/2;
        int totalSum=OrigSum-arrSum;
        return totalSum;
    }
};
```
## java
```java
// User function Template for Java
class Solution {

    // Note that the size of the array is n-1
    int missingNumber(int n, int arr[]) {
int arrSum=0;
        for(int i=0;i<n-1;i++){
            arrSum+=arr[i];
        }
int OrigSum=(n*(n+1))/2;
        int totalSum=OrigSum-arrSum;
        return totalSum;
    

    }
}
```
