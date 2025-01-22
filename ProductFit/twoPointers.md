## Two Pointers


The two-pointer technique is a common algorithmic approach used to solve problems involving searching or iterating through arrays, strings, or linked lists.

It involves using two indices (pointers) to traverse the data structure in a specific way.

Two pointers reduce unnecessary computations and efficiently find the solution to the problem.

- unidirectional
- inwards directional
- staged directional

 when to use
 ------------

 - When the problem involves searching for pairs, triplets, or subarrays.
 - When the data structure is sorted or can be sorted.
 - When the goal is to optimize the solution to linear or near-linear complexity.-

### unidirectional

**1.move zeros**

leetcode-283

```java
class Solution {
    public void moveZeroes(int[] nums) {

        int left=0;
        int right=0;

        while(right<nums.length){
            if(nums[right]==0){
                right++;
            }
            else{
                int temp=nums[right];
                nums[right]=nums[left];
                nums[left]=temp;
                left++;
                right++;
            }
        }
        
    }
}
```



### inward directional

**1.two sum**

leetcode-1



```java
import java.util.Arrays;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        // Step 1: Store the original indices with the numbers
        int[][] numsWithIndices = new int[nums.length][2];
        for (int i = 0; i < nums.length; i++) {
            numsWithIndices[i][0] = nums[i]; // Value
            numsWithIndices[i][1] = i;      // Original Index
        }

        // Step 2: Sort the array by values
        Arrays.sort(numsWithIndices, (a, b) -> Integer.compare(a[0], b[0]));

        // Step 3: Use two-pointer technique to find the target sum
        int left = 0, right = numsWithIndices.length - 1;
        while (left < right) {
            int sum = numsWithIndices[left][0] + numsWithIndices[right][0];
            if (sum < target) {
                left++;
            } else if (sum > target) {
                right--;
            } else {
                // Return the original indices
                return new int[] {numsWithIndices[left][1], numsWithIndices[right][1]};
            }
        }

        // Step 4: If no solution exists, throw an exception
        throw new IllegalArgumentException("No two sum solution");
    }
}

```
**2.three sum**

leetcode-15


```java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {

        int n=nums.length;
        Arrays.sort(nums);
        List<List<Integer>> result=new ArrayList<>();

        for(int i=0;i<n-2;i++){
            if(i!=0 && nums[i-1]==nums[i]) continue;
            int left=i+1;int right=n-1;
            while(left<right){
                int sum=nums[i]+nums[left]+nums[right];
                if(sum<0){
                    left++;
                }
                else if(sum>0){
                    right--;
                }
                else if(sum==0){
                    List<Integer>temp=Arrays.asList(nums[i],nums[left],nums[right]);
                    result.add(temp);
                    left++;
                    right--;

                    while(left<right && nums[left-1]==nums[left])left++;
                    while(left<right && nums[right+1]==nums[right]) right--;
                    
                }
            }
        }
        return result;
        
    }
}
```
**3.container with most water**

leetcode-11


```java
class Solution {
    public int maxArea(int[] height) {
        int n = height.length;
        int left = 0, right = n - 1;
        int max = 0;

        while (left < right) {
            int minHeight = Math.min(height[left], height[right]);
            int width = right - left;
            int area = minHeight * width;

            max = Math.max(max, area);

            // Move the pointer pointing to the shorter line inward
            if (height[left] < height[right]) {
                left++;
            } else {
                right--;
            }
        }

        return max;
    }
}

```

**4.valid palindrome**

leetcode-125

```java

class Solution {
    public boolean isPalindrome(String s) {
        StringBuilder filtered = new StringBuilder();
        for(int i=0;i<s.length();i++){
            char c=s.charAt(i);
            if(Character.isLetterOrDigit(c)){
                filtered.append(Character.toLowerCase(c));
            }
        }
int l=filtered.length();
        for(int i=0;i<l/2;i++){
            if(filtered.charAt(i)!=filtered.charAt(l-1-i)){
                return false;
            }
        }
        return true;
    }
}
```


### staged directional

**1.next permutation**

leetcode-31

```java
class Solution {
    public void nextPermutation(int[] nums) {
        int n=nums.length;
        int i=n-2;
        while(i>=0 && nums[i]>=nums[i+1]){
            i--;
        }
        if(i>=0){
            int j=n-1;
            while(nums[j]<=nums[i]){
                j--;
            }
            swap(nums,i,j);
        }
        reverse(nums,i+1);
        
    }
    public void swap(int[] nums,int i,int j){
        int temp=nums[i];
        nums[i]=nums[j];
        nums[j]=temp;

    }
    public void reverse(int[] nums,int start){
        int end=nums.length-1;
        while(start<end){
            swap(nums,start,end);
            start++;
            end--;
        }
    }
}
```

**2.Next Greater Element I**

leetcode-496

```java
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        ArrayList<Integer> arr=new ArrayList<>();
        for(int i=0;i<nums1.length;i++){
           int index=-1;
            for(int j=0;j<nums2.length-1;j++){
                if(nums1[i]==nums2[j]){
                    index=j;
                    break;
                }   
                         
            }

            int nextGreater=-1;
           if(index!=-1){
             for(int k=index+1;k<nums2.length;k++){
                if(nums2[k]>nums1[i]){
                    nextGreater=nums2[k];
                    
                    break;
                }
            }
           }
            arr.add(nextGreater);
           
        }
        int[] result=new int[arr.size()];
        for(int l=0;l<result.length;l++){
            result[l]=arr.get(l);
        }
        return result;
    }
}
```
