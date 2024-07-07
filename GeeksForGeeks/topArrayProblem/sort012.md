### Sort 0s, 1s and 2s
##### [https://www.geeksforgeeks.org/problems/sort-an-array-of-0s-1s-and-2s4231/1]
## c
```c
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}


void sort012(int a[], int n) {
    int low = 0, mid = 0, high = n - 1;
    
    while (mid <= high) {
        switch (a[mid]) {
            case 0:
                swap(&a[low], &a[mid]);
                low++;
                mid++;
                break;
            case 1:
                mid++;
                break;
            case 2:
                swap(&a[mid], &a[high]);
                high--;
                break;
        }
    }
}
```
## cpp
```cpp

class Solution
{
    public:
    void sort012(int a[], int n)
    {
        // code here 
        sort(a,a+n);
    }
    
};
```
## java
```java
  class Solution
    {
        public static void sort012(int a[], int n)
        {
            // code here 
            Arrays.sort(a);
        }
    }
```
