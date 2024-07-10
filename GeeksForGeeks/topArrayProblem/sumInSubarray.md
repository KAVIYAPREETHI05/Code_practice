### Indexes of Subarray Sum
## c
```c
void subarraySum(int arr[], int n, long long s, int result[]) {
    int left = 0;
    int right = 0;
    int currSum = 0;

    while (right < n) {
        currSum += arr[right];
        while (currSum > s && left < right) {
            currSum -= arr[left];
            left++;
        }
        if (currSum == s) {
            result[0] = left + 1;
            result[1] = right + 1;
            return;
        }
        right++;
    }
    result[0] = -1;
}
```
## cpp
```cpp
class Solution {
  public:
    // Function to find a continuous sub-array which adds up to a given number.
    vector<int> subarraySum(vector<int> arr, int n, long long s) {
       // if(sum==0) return -1;
       int left=0;
       int right=0;
       int currSum=0;
       
       while(right<n){
           currSum+=arr[right];
           while(currSum>s && left<right){
               currSum-=arr[left];
               left++;
           }
           if(currSum==s){
               return {left+1,right+1};
           }
                      right++;

       }
       return {-1};
}
};
```
## java
```java
class Solution {
    // Function to find a continuous sub-array which adds up to a given number.
    static ArrayList<Integer> subarraySum(int[] arr, int n, int s) {
        ArrayList<Integer> result=new ArrayList<>();
    
       int left=0;
       int right=0;
       int currSum=0;
       
       while(right<n){
           currSum+=arr[right];
           while(currSum>s && left<right){
               currSum-=arr[left];
               left++;
           }
           if(currSum==s){
               result.add(left+1);
               result.add(right+1);
               return result;
           }
                      right++;

       }
       result.add(-1);
       return result;
      
    }
}
```
