### Max sum path in two arrays
```java

class Solution {
    public int maxPathSum(List<Integer> arr1, List<Integer> arr2) {
    
        int m = arr1.size();
        int n = arr2.size();
        
        // Pointers for arr1 and arr2
        int i = 0, j = 0;
        
        // Sum of paths for arr1 and arr2
        int sum1 = 0, sum2 = 0;
        
        // Result to store the maximum path sum
        int result = 0;
        
        while (i < m && j < n) {
            // If the element in arr1 is smaller, add it to sum1
            if (arr1.get(i) < arr2.get(j)) {
                sum1 += arr1.get(i);
                i++;
            } 
            // If the element in arr2 is smaller, add it to sum2
            else if (arr1.get(i) > arr2.get(j)) {
                sum2 += arr2.get(j);
                j++;
            } 
            // If the elements are the same, take the maximum of the two sums
            else {
                result += Math.max(sum1, sum2) + arr1.get(i);
                sum1 = 0;
                sum2 = 0;
                i++;
                j++;
            }
        }
        
        // Add remaining elements in arr1 to sum1
        while (i < m) {
            sum1 += arr1.get(i);
            i++;
        }
        
        // Add remaining elements in arr2 to sum2
        while (j < n) {
            sum2 += arr2.get(j);
            j++;
        }
        
        // Add the maximum of the remaining sums to the result
        result += Math.max(sum1, sum2);
        
        return result;
    }
}

```
