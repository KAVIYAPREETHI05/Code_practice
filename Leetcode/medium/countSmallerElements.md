### 1365. How Many Numbers Are Smaller Than the Current Number
##### [https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/]
## c
```c
int* smallerNumbersThanCurrent(int* nums, int numsSize, int* returnSize) {
        int n=numsSize;
    int* answer=(int*)malloc(n*(sizeof(int)));
    for(int i=0;i<n;i++){
        int count=0;
        for(int j=0;j<n;j++){
            if(i!=j && nums[j]<nums[i]){
                count++;
            }
        }
        answer[i]=count;
    }
    *returnSize=n;
    return answer;
    
}
```
## cpp
```cpp
class Solution {
public:
    vector<int> smallerNumbersThanCurrent(vector<int>& nums) {
         int n=nums.size();
    vector<int>answer(n,0);
    for(int i=0;i<n;i++){
        int count=0;
        for(int j=0;j<n;j++){
            if(i!=j && nums[j]<nums[i]){
                count++;
            }
        }
        answer[i]=count;
    }
    
    return answer;
    
} 
};
```
### java
```java
class Solution {
    public int[] smallerNumbersThanCurrent(int[] nums) {
         int n=nums.length;
    int[]answer=new int[n];
    for(int i=0;i<n;i++){
        int count=0;
        for(int j=0;j<n;j++){
            if(i!=j && nums[j]<nums[i]){
                count++;
            }
        }
        answer[i]=count;
    }
    
    return answer;
    
} 
}
```
