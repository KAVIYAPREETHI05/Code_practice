### Move all negative elements to end
##### [https://www.geeksforgeeks.org/problems/move-all-negative-elements-to-end1813/1]
## c
```c

 void segregateElements(int arr[],int n) {
     int temp[n];
      int index=0;
      for(int i=0;i<n;i++){
          if(arr[i]>=0){
              temp[index++]=arr[i];
          }
      }
      for(int i=0;i<n;i++){
          if(arr[i]<0){
              temp[index++]=arr[i];
          }
      }
      for(int i=0;i<n;i++){
          arr[i]=temp[i];
      }
 }
```
## cpp
```cpp
class Solution {
public:
 void segregateElements(vector<int>& arr) {
      int n=arr.size();
      vector<int>temp(n);
      int index=0;
      for(int i=0;i<n;i++){
          if(arr[i]>=0){
              temp[index++]=arr[i];
          }
      }
      for(int i=0;i<n;i++){
          if(arr[i]<0){
              temp[index++]=arr[i];
          }
      }
      for(int i=0;i<n;i++){
          arr[i]=temp[i];
      }
 }
};

```
## java
```java

class Solution {
    public void segregateElements(int[] arr) {
         int n=arr.length;
      int[] temp=new int[n];
      int index=0;
      for(int i=0;i<n;i++){
          if(arr[i]>=0){
              temp[index++]=arr[i];
          }
      }
      for(int i=0;i<n;i++){
          if(arr[i]<0){
              temp[index++]=arr[i];
          }
      }
      for(int i=0;i<n;i++){
          arr[i]=temp[i];
      }
 
        // Your code goes here
    }
}
```
