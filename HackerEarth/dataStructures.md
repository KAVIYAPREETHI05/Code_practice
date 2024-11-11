### Minimum length
##### [https://www.hackerearth.com/practice/data-structures/arrays/1-d/practice-problems/algorithm/minimum-length-4-945227e2/]

```java
import java.util.*;

class TestClass {
    public static void main(String args[] ) throws Exception {

        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt(); // number of test cases
        
        while (t-- > 0) {
            int n = sc.nextInt(); // length of the arrays
            int[] arr1 = new int[n];
            int[] arr2 = new int[n];
            
            for (int i = 0; i < n; i++) {
                arr1[i] = sc.nextInt();
            }
            
            for (int i = 0; i < n; i++) {
                arr2[i] = sc.nextInt();
            }
            
            // Find the first and last positions where arr1 and arr2 differ
            int left = -1, right = -1;
            
            // Check the positions where arr1 and arr2 differ
            for (int i = 0; i < n; i++) {
                if (arr1[i] != arr2[i]) {
                    if (left == -1) left = i; // first difference
                    right = i; // last difference
                }
            }
            
            // If there's no difference, then they are already the same
            if (left == -1) {
                System.out.println(0);
            } else {
                System.out.println(right - left + 1);
            }
        }
        
        sc.close();
    }
}

```
