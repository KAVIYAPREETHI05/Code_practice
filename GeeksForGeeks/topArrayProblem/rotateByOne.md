### Rotate Array by one
##### [https://www.geeksforgeeks.org/problems/cyclically-rotate-an-array-by-one2614/1]
## cpp
```cpp

class Solution {
  public:
    void rotate(vector<int> &arr) {
        // code here
        int n=arr.size();
        int temp=arr[n-1];
        for(int i=n-1;i>=0;i--){
            arr[i]=arr[i-1];
        }
        arr[0]=temp;
    }
};
```
## java
```java
class Solution {
    public void rotate(int[] arr) {
        
        int n=arr.length;
        int temp=arr[n-1];
        for(int i=n-1;i>0;i--){
            arr[i]=arr[i-1];
        }
        arr[0]=temp;
    
    }
}
```
