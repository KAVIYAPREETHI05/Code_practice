### Union of two arrays
##### [https://www.geeksforgeeks.org/problems/union-of-two-arrays3538/1]
## cpp
```cpp
class Solution {
  public:
    // Function to return the count of number of elements in union of two arrays.
  
        bool isPresent(const int arr[], int n, int key) {
    for (int i = 0; i < n; ++i) {
        if (arr[i] == key) {
            return true;
        }
    }
    return false;
}

// Function to find union of two arrays
  int doUnion(vector<int> arr1, vector<int> arr2) {
        int n1=arr1.size();
        int n2=arr2.size();
    int unionArr[n1 + n2]; // Array to store union elements
    int unionSize = 0; // Size of union array

    // Insert elements of arr1 into unionArr
    for (int i = 0; i < n1; ++i) {
        if (!isPresent(unionArr, unionSize, arr1[i])) {
            unionArr[unionSize++] = arr1[i];
        }
    }

    // Insert elements of arr2 into unionArr
    for (int i = 0; i < n2; ++i) {
        if (!isPresent(unionArr, unionSize, arr2[i])) {
            unionArr[unionSize++] = arr2[i];
        }
    }

    return unionSize;
}
     
};
```
```cpp
//optimized code
class Solution {
  public:
    // Function to return the count of number of elements in union of two arrays.
    int doUnion(vector<int> arr1, vector<int> arr2) {
        int n1=arr1.size();
        int n2=arr2.size();
         unordered_set<int> unionSet;

    // Insert all elements of arr1 into unionSet (handles duplicates automatically)
    for (int i = 0; i < n1; ++i) {
        unionSet.insert(arr1[i]);
    }

    // Insert all elements of arr2 into unionSet (handles duplicates automatically)
    for (int i = 0; i < n2; ++i) {
        unionSet.insert(arr2[i]);
    }

    // Size of unionSet gives the number of unique elements in the union
    return unionSet.size();
}
};
```
## java
```java
import java.util.HashSet;

public class Main {
    
    // Function to find union of two arrays
    public static int findUnion(int[] arr1, int[] arr2) {
        HashSet<Integer> unionSet = new HashSet<>();

        // Insert all elements of arr1 into unionSet (handles duplicates automatically)
        for (int num : arr1) {
            unionSet.add(num);
        }

        // Insert all elements of arr2 into unionSet (handles duplicates automatically)
        for (int num : arr2) {
            unionSet.add(num);
        }

        // Size of unionSet gives the number of unique elements in the union
        return unionSet.size();
    }

    public static void main(String[] args) {
        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = {1, 2, 3};

        int unionSize = findUnion(arr1, arr2);
        System.out.println("Number of elements in the union: " + unionSize);
    }
}
```
