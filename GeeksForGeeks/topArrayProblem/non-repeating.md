### Non-Repeating Element
##### [https://www.geeksforgeeks.org/problems/non-repeating-element3958/1]
### c
```c
#include <stdio.h>
int main() {
    int n;
    int arr[] = {-1,2,-1,2,3};
    n = sizeof(arr) / sizeof(arr[0]);
    int max = arr[0];
    int min=arr[0];
    for (int i = 0; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
        else if(arr[i]<min){
            min=arr[i];
        }
    }
    int range=max-min+1;
    int freq[range];
    for (int i = 0; i <range; i++) {
        freq[i]=0; 
    }

    for (int i = 0; i <n; i++) {
        freq[arr[i]-min]++; 
    }
    int found=1;
    for(int i=0;i<n;i++){
        if(freq[arr[i]-min]==1){
            printf("%d ",arr[i]);
            found=0;
        }
            }
            if(found){
                printf("0");
            }
   
    return 0;
}

```
### cpp
```cpp
class Solution {
  public:
    int firstNonRepeating(vector<int>& arr) {
     int n=arr.size();
    int max = arr[0];
    int min=arr[0];
    for (int i = 0; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
        else if(arr[i]<min){
            min=arr[i];
        }
    }
    int range=max-min+1;
    int freq[range];
    for (int i = 0; i <range; i++) {
        freq[i]=0; 
    }

    for (int i = 0; i <n; i++) {
        freq[arr[i]-min]++; 
    }
    int found=1;
    for(int i=0;i<n;i++){
        if(freq[arr[i]-min]==1){
            return arr[i];
            found=0;
        }
            }
            if(found){
                return 0;
            }

    }
};
```
### java
```java
class Solution {
    public int firstNonRepeating(int[] arr) {
       
     int n=arr.length;
    int max = arr[0];
    int min=arr[0];
    for (int i = 0; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
        else if(arr[i]<min){
            min=arr[i];
        }
    }
    int range=max-min+1;
    int[]freq=new int[range];
    for (int i = 0; i <range; i++) {
        freq[i]=0; 
    }

    for (int i = 0; i <n; i++) {
        freq[arr[i]-min]++; 
    }
    boolean found=true;
    for(int i=0;i<n;i++){
        if(freq[arr[i]-min]==1){
            found=false;
            return arr[i];
            
        }
            }
            
                return 0;
    }
}
```
