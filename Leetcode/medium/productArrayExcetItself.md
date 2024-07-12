### 238. Product of Array Except Self
##### [https://leetcode.com/problems/product-of-array-except-self/description/]
## c
```c


int* productExceptSelf(int* nums,int numsSize,int* returnSize){
    int n=numsSize;
    int* answer=(int*) malloc(n*(sizeof(int)));
    int zeros=0;
    int product=1;
    for(int i=0;i<n;i++){
        answer[i]=0;
    }
    for(int i=0;i<n;i++){
        if(nums[i]==0){
            zeros++;
        }
        else{
            product*=nums[i];
        }
    }
    if(zeros==0){
        for(int i=0;i<n;i++){
            answer[i]=product/nums[i];
        }
    }
    else if(zeros==1){
        for(int i=0;i<n;i++){
            if (nums[i]==0){
                answer[i]=product;
                  }
                  else{
                    answer[i]=0;
                  }
        }
    }
    *returnSize=n;
    return answer;

}
```
## cpp
```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
    int n=nums.size();
    vector<int> answer(n,0);
    int zeros=0;
    int product=1;
    
    for(int i=0;i<n;i++){
        if(nums[i]==0){
            zeros++;
        }
        else{
            product*=nums[i];
        }
    }
    if(zeros==0){
        for(int i=0;i<n;i++){
            answer[i]=product/nums[i];
        }
    }
    else if(zeros==1){
        for(int i=0;i<n;i++){
            if (nums[i]==0){
                answer[i]=product;
                  }
                  else{
                    answer[i]=0;
                  }
        }
    }

    return answer;

}
  };
```
### java
```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
    int n=nums.length;
    int[]answer=new int[n];
    int zeros=0;
    int product=1;
    for(int i=0;i<n;i++)
    answer[i]=0;
    for(int i=0;i<n;i++){
        if(nums[i]==0){
            zeros++;
        }
        else{
            product*=nums[i];
        }
    }
    if(zeros==0){
        for(int i=0;i<n;i++){
            answer[i]=product/nums[i];
        }
    }
    else if(zeros==1){
        for(int i=0;i<n;i++){
            if (nums[i]==0){
                answer[i]=product;
                  }
                  else{
                    answer[i]=0;
                  }
        }
    }

    return answer;

}
        
    
}
```
