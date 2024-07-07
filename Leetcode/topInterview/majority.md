### 169. Majority Element
##### [https://leetcode.com/problems/majority-element/description/?envType=study-plan-v2&envId=top-interview-150]
## c
```c
int majorityElement(int* arr, int numsSize) {
   int count=0;
   int candidate=0;
   for(int i=0;i<numsSize;i++){
    if(count==0){
        candidate=arr[i];
        count=1;
    }
    else if(arr[i]==candidate){
        count++;
    }
    else{
        count--;
    }
   }
   count=0;
   for(int i=0;i<numsSize;i++){
    if(arr[i]==candidate){
        count++;
    }
       if(count>numsSize/2){
    return arr[i];
   }
   }
   return -1;
}
```
## cpp
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {

        sort(nums.begin() , nums.end());

        return nums[nums.size()/2];
        
    }
};
```
## java
```java
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length/2];        
    }
}
```
