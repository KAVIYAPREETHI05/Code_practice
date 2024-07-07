### Find the Frequency
##### [https://www.geeksforgeeks.org/problems/find-the-frequency/1]
## cpp
```cpp
int findFrequency(vector<int> Arr, int X){
    int count= 0;
    int N=Arr.size();
    // Your code here
    for(int i=0;i<N;i++){
        if(Arr[i]==X){
            count++;
        }
    }
    return count;
}
```
## java
```java
class Solution{
    int findFrequency(int Arr[], int X){
         int count= 0;
    // Your code here
    for(int i=0;i<Arr.length;i++){
        if(Arr[i]==X){
            count++;
        }
    }
    return count;
}
        
    }
```
