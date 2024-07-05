### 27.Remove Element
##### [https://leetcode.com/problems/remove-element/description/?envType=study-plan-v2&envId=top-interview-150]
## c
```c
int removeElement(int* nums, int numsSize, int val) {
    int count=0;int k=0;
    for(int i=0;i<numsSize;i++){
        if(nums[i]!=val){
            nums[k++]=nums[i];
            count++;
        }
    }
    return count;
}
```
## cpp
```cpp
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int k = 0;
        for(auto it = nums.begin(); it != nums.end();){
            if(*it == val){
                nums.erase(it);
            }else{
                k++;
                it++;
            }
        }
        return k;
    }
};
```
## java
```java
class Solution {
    public int removeElement(int[] nums, int val) {
         int count=0;int k=0;
    for(int i=0;i<nums.length;i++){
        if(nums[i]!=val){
            nums[k++]=nums[i];
            count++;
        }
    }
    return count;    
}   
}
```
