### 26. Remove Duplicates from Sorted Array
##### [https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/?envType=study-plan-v2&envId=top-interview-150]
## c
```C

int removeDuplicates(int* arr, int numsSize) {
    if(numsSize==0){
        return 0;
    }
    int j=0;
    for(int i=0;i<numsSize-1;i++){
        if(arr[i]!=arr[i+1]){
            arr[j++]=arr[i];
        }
    }
    arr[j++]=arr[numsSize-1];
    return j;
   }
```
## cpp
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if (nums.empty()) {
            return 0;
        }

        int k = 1; // Initialize the count of unique elements to 1
        for (int i = 1; i < nums.size(); i++) {
            if (nums[i] != nums[i - 1]) {
                nums[k] = nums[i]; // Overwrite the next unique element
                k++;
            }
        }        
        return k;
    }
};
```
## java
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if(nums.length==0){
            return 0;
        }int k=0;
        for(int i=0;i<nums.length-1;i++){
            if(nums[i]!=nums[i+1]){
                nums[k++]=nums[i];
            }
        }
nums[k++]=nums[nums.length-1];
return k;        
    }
}
```
