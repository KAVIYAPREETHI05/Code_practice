### 189. Rotate Array
##### [https://leetcode.com/problems/rotate-array/description/?envType=study-plan-v2&envId=top-interview-150]
## c
```c
void reversal(int arr[],int start,int end){
    while(start<end){
        int temp=arr[start];
        arr[start]=arr[end];
        arr[end]=temp;
        start++;
        end--;
    }
}
void rotate(int* arr, int numsSize, int k) {
   k=k%numsSize;
   if (k==0) return;
   reversal(arr,0,numsSize-1);
   reversal(arr,0,k-1);
   reversal(arr,k,numsSize-1);
}
```
## cpp
```cpp
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int n=nums.size();
        k=k%n;
   if (k==0) return;
   reverse(nums,0,n-1);
   reverse(nums,0,k-1);
   reverse(nums,k,n-1);
    }
private:
    void reverse(std::vector<int>& nums, int start, int end) {
        while (start < end) {
            std::swap(nums[start], nums[end]);
            start++;
            end--;
        }
    }
           
};
```
## java
```
class Solution {
    public void rotate(int[] nums, int k) {
        int n=nums.length;
        k=k%n;
        if(k==0) return;
        reverse(nums,0,n-1);
        reverse(nums,0,k-1);
        reverse(nums,k,n-1);
        
    }
   
    void reverse(int[]nums,int start,int end){
        while(start<end){
            int temp=nums[start];
            nums[start]=nums[end];
            nums[end]=temp;
            start++;
            end--;
        }
    }
}
```
