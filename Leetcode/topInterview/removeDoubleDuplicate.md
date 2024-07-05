### 80. Remove Duplicates from Sorted Array II
##### [https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/description/?envType=study-plan-v2&envId=top-interview-150]
## c
```C
int removeDuplicates(int* arr, int size){
    int k=1;
        if(size==0){
            return 0;
        }        
            for(int i=1;i<size;i++){
                if(k<2 || arr[i]!=arr[k-2]){
                    arr[k++]=arr[i];
                }
                 }
          return k;
}
```
## cpp
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& arr) {
        int k=1;
        if(arr.size()==0){
            return 0;
        }       
            for(int i=1;i<arr.size();i++){
                if(k<2 || arr[i]!=arr[k-2]){
                    arr[k++]=arr[i];
                }            
        }   
    return k;
         }
};
```
## java
```java
class Solution {
    public int removeDuplicates(int[] arr) {
        int k=1;
        if(arr.length==0){
            return 0;
        }        
            for(int i=1;i<arr.length;i++){
                if(k<2 || arr[i]!=arr[k-2]){
                    arr[k++]=arr[i];
                }
            }
     return k;
    }
}
```
