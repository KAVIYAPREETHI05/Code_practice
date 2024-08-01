### First Repeating Element
##### [https://www.geeksforgeeks.org/problems/first-repeating-element4018/1]
### c
```c
#include <stdio.h>
#include <limits.h>  // For INT_MAX
int main() {
    int n;
    int arr[] = {1,5,3,4,3,5,6};
    n = sizeof(arr) / sizeof(arr[0]);
    int max = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    int freq[max + 1];
    for (int i = 0; i <= max; i++) {
        freq[i] = -1; 
    }
    int min_index=INT_MAX;
    for(int i=0;i<n;i++){
        if(freq[arr[i]]==-1){
            freq[arr[i]]=i;
        }
        else{
            if(freq[arr[i]]<min_index){
                min_index=freq[arr[i]];
            }
        }
    }
    if(min_index==INT_MAX){
        printf("-1");
    }
    else{
        printf("%d",min_index+1);
    }
    return 0;
}

```
### cpp
```cpp
class Solution {
  public:
    // Function to return the position of the first repeating element.
    int firstRepeated(vector<int> &arr) {
        
      int n=arr.size();
    int max = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    vector<int>freq(max+1,-1);
    
    int min_index=INT_MAX;
    for(int i=0;i<n;i++){
        if(freq[arr[i]]==-1){
            freq[arr[i]]=i;
        }
        else{
            if(freq[arr[i]]<min_index){
                min_index=freq[arr[i]];
            }
        }
    }
    if(min_index==INT_MAX){
        return -1;
    }
    else{
        return min_index+1;
    }
    }
};
```

### java
```java
class Solution {
    // Function to return the position of the first repeating element.
    public static int firstRepeated(int[] arr) {
        
         int n=arr.length;
    int max = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    int[] freq=new int[max+1];
    for (int i = 0; i <= max; i++) {
        freq[i] = -1; 
    }
    
    int min_index=Integer.MAX_VALUE;
    for(int i=0;i<n;i++){
        if(freq[arr[i]]==-1){
            freq[arr[i]]=i;
        }
        else{
            if(freq[arr[i]]<min_index){
                min_index=freq[arr[i]];
            }
        }
    }
    if(min_index==Integer.MAX_VALUE){
        return -1;
    }
    else{
        return min_index+1;
    }
        
    }
}
```
