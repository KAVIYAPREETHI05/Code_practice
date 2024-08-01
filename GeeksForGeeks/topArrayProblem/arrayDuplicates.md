### array Duplicates
##### [https://www.geeksforgeeks.org/problems/find-duplicates-in-an-array/1] 
### c
```c
// Online C compiler to run C program online
#include <stdio.h>
int main() {
    int n;
    int arr[]={2,3,1,2,3};
    n=sizeof(arr)/sizeof(arr[0]);
    int max=arr[0];
    for(int i=0;i<n;i++){
        if(arr[i]>max){
            max=arr[i];
        }
    }
    int freq[max+1];
    for(int i=0;i<=max;i++){
        freq[i]=0;
    }
    for(int i=0;i<n;i++){
        freq[arr[i]]++;
    }
    int found=1;
    for(int i=0;i<=max;i++){
        if(freq[i]>1){
            printf("%d ",i);
            found=0;
        }
    }
    if(found){
        printf("-1");
    }
    return 0;
}
```

### cpp
```cpp
class Solution {
  public:
    vector<int> duplicates(vector<long long> arr) {
        // code here
        int n=arr.size();
    vector <long long> temparr(n+1,0);
    vector<int> result;
    for(int i=0;i<n;i++){
        temparr[arr[i]]++;
    }
    for(int i=0;i<n;i++){
        if(temparr[i]>1){
            result.push_back(i);
        }
    }
    if(result.empty()){
        result.push_back(-1);
    }
    return result;
    }
};
```

### java
```java
class Solution {
    public static ArrayList<Integer> duplicates(int[] arr) {
    
        int n=arr.length;
        ArrayList<Integer> result=new ArrayList<>();
       
           int maxValue = Arrays.stream(arr).max().orElse(0);
            int[] temparr=new int[maxValue+1];
       for(int i=0;i<=maxValue;i++){
           temparr[i]=0;
       }
        for(int i=0;i<n;i++){
            temparr[arr[i]]++;
        }
        for(int i=0;i<=maxValue;i++){
            if(temparr[i]>1){
                result.add(i);
                
            }
        }
        if(result.isEmpty()){
            result.add(-1);
        }
        return result;
    }
    }
```
