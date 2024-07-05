### 88. Merge Sorted Array
##### [https://leetcode.com/problems/merge-sorted-array/description/?envType=study-plan-v2&envId=top-interview-150]

## c
```c
void merge(int* nums1, int nums1Size, int m, int* nums2, int nums2Size, int n)
{
    int i = m - 1; 
    int j = n - 1; 
    int k = nums1Size - 1; 
    while (i >= 0 && j >= 0)
    {
        if (nums1[i] > nums2[j])
        {
            nums1[k--] = nums1[i--];
        }
        else
        {
            nums1[k--] = nums2[j--];
        }
    }

     while (j >= 0)
    {
        nums1[k--] = nums2[j--];
    }
}
```
## java
```java

class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i=m-1;
        int j=n-1;
        int k=m+n-1;
        while(i>=0 && j>=0){
            if(nums1[i]>nums2[j]){
                nums1[k--]=nums1[i--];
            }
            else{
                nums1[k--]=nums2[j--];
            }
        }
        while(j>=0){
            nums1[k--]=nums2[j--];
        }
        
    }
}
```
