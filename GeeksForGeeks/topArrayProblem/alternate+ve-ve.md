### Alternate positive and negative numbers
##### [https://www.geeksforgeeks.org/problems/array-of-alternate-ve-and-ve-nos1401/1]
### c
```c
#include <stdio.h>
int main() {
    int n;
    int arr[] = {-5, -2, 5, 2, 4, 7, 1, 8, 0, -8};
    n = sizeof(arr) / sizeof(arr[0]);
    int positive[n]; int negative[n];
    int pos_size=0;int neg_size=0;
   for(int i=0;i<n;i++){
       if(arr[i]>=0){
           positive[pos_size++]=arr[i];
       }
       else if(arr[i]<0){
           negative[neg_size++]=arr[i];
           
       }
   }
   int pos_index=0;int neg_index=0;
   int i=0;int j=0;
   while(pos_index<pos_size && neg_index<neg_size){
       printf("%d ",positive[pos_index++]);
       printf("%d ",negative[neg_index++]);
   }
   while(pos_index<pos_size){
       printf("%d ",positive[pos_index++]);
       
   }
   while(neg_index<neg_size++){
       printf("%d ",negative[neg_index++]);
   }
    return 0;
}
//5 -5 2 -2 4 -8 7 1 8 0
```
### cpp
```cpp
class Solution {
public:
    void rearrange(int arr[], int n) {
        int positive[n];
        int negative[n];
        int pos_size = 0;
        int neg_size = 0;

        // Separate positive and negative numbers
        for (int i = 0; i < n; i++) {
            if (arr[i] >= 0) {
                positive[pos_size++] = arr[i];
            } else {
                negative[neg_size++] = arr[i];
            }
        }

        int pos_index = 0;
        int neg_index = 0;
        int index=0;

        // Interleave positive and negative numbers
        while (pos_index < pos_size && neg_index < neg_size) {
            arr[index++]= positive[pos_index++] ;
            arr[index++]=negative[neg_index++] ;
        }

        // Print remaining positives, if any
        while (pos_index < pos_size) {
            arr[index++]=  positive[pos_index++];
        }

        // Print remaining negatives, if any
        while (neg_index < neg_size) {
            arr[index++]= negative[neg_index++];
        }

        
    }
};
```
### java
```java

class Solution {
    void rearrange(int arr[], int n) {
        
        int[] positive=new int[n];
        int[] negative=new int[n];
        int pos_size = 0;
        int neg_size = 0;

        // Separate positive and negative numbers
        for (int i = 0; i < n; i++) {
            if (arr[i] >= 0) {
                positive[pos_size++] = arr[i];
            } else {
                negative[neg_size++] = arr[i];
            }
        }

        int pos_index = 0;
        int neg_index = 0;
        int index=0;

        // Interleave positive and negative numbers
        while (pos_index < pos_size && neg_index < neg_size) {
            arr[index++]= positive[pos_index++] ;
            arr[index++]=negative[neg_index++] ;
        }

        // Print remaining positives, if any
        while (pos_index < pos_size) {
            arr[index++]=  positive[pos_index++];
        }

        // Print remaining negatives, if any
        while (neg_index < neg_size) {
            arr[index++]= negative[neg_index++];
        }
    }
}
```
