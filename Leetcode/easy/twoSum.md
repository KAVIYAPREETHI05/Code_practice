### 1.Two sum
##### [https://leetcode.com/problems/two-sum/]

### java
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] result=new int[2];
        int n=nums.length;
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                if(nums[i]+nums[j]==target){
                    result[0]=i;
                    result[1]=j;

                }
            }
        }
       return result; 
    }
}
```
### c
```c
int *twoSum(int *nums, int numsSize, int target, int *returnSize){
*returnSize=2;
    int *returnvalues= malloc((*returnSize) * sizeof(int));
    for(int i=0;i<numsSize-1;i++){
        for(int j=i+1;j<numsSize;j++){
            if(nums[i]+nums[j]==target){
                returnvalues[0]=i;
                returnvalues[1]=j;
                break;
            }
        }
    }
    return returnvalues;
    
}
```
### cpp
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
       int n=nums.size();
       vector<int> result;
       for(int i=0;i<n-1;i++){
        for(int j=i+1;j<n;j++){
            if(nums[i]+nums[j]==target){
                result.push_back(i);
                result.push_back(j);
                break;
            }
        }
       }
       return result;
}
};
```
