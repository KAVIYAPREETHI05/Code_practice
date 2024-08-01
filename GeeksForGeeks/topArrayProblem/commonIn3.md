### Common in 3 Sorted Arrays

```c
#include <stdio.h>
void insertionSort(int arr[],int n){
    int key,j;
    for(int i=1;i<n;i++){
        key=arr[i];
        j=i-1;
        while(j>=0 && arr[j]>key){
            arr[j+1]=arr[j];
            j=j-1;
        }
        arr[j+1]=key;
        
    }
}
void findCommonElements(int arr1[],int m,int arr2[],int n,int arr3[],int o){
    int i,j,k;
    i=j=k=0;
    while(i<m && j<n && k<o){
        if(arr1[i]==arr2[j] && arr2[j]==arr3[k]){
            printf("%d ",arr1[i]);
            i++;j++;k++;
        }
        else if(arr1[i]<arr2[j]){
            i++;
        }
        else if(arr2[j]<arr3[k]){
            j++;
        }
        else{
            k++;
        }
    }
}
int main() {
    int arr1[] = {1, 2, 3, 1};
    int arr2[] = {3, 4, 5, 6};
    int arr3[] = {2, 3, 7, 4};

    int m = sizeof(arr1) / sizeof(arr1[0]);
    int n = sizeof(arr2) / sizeof(arr2[0]);
    int o = sizeof(arr3) / sizeof(arr3[0]);

    // Sort the arrays using insertion sort
    insertionSort(arr1, m);
    insertionSort(arr2, n);
    insertionSort(arr3, o);

    // Find and print common elements
    findCommonElements(arr1, m, arr2, n, arr3, o);
    return 0;
}

```
### cpp
```cpp
class Solution {
  public:
    // Function to find common elements in three arrays.
    vector<int> commonElements(vector<int> &arr1, vector<int> &arr2,
                               vector<int> &arr3) {
        
         int i,j,k;
    i=j=k=0;
    int m=arr1.size();
    int n=arr2.size();
    int o=arr3.size();
    vector<int>result;
    unordered_set<int>seen;
    while(i<m && j<n && k<o){
        if(arr1[i]==arr2[j] && arr2[j]==arr3[k]){
            if(seen.find(arr1[i])== seen.end()){
                            result.push_back(arr1[i]);
                            seen.insert(arr1[i]);

            }
            i++;j++;k++;
        }
        else if(arr1[i]<arr2[j]){
            i++;
        }
        else if(arr2[j]<arr3[k]){
            j++;
        }
        else{
            k++;
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
    // Function to find common elements in three arrays.
    public List<Integer> commonElements(List<Integer> arr1, List<Integer> arr2,
                                        List<Integer> arr3) {
       
        
         int i,j,k;
    i=j=k=0;
    int m=arr1.size();
    int n=arr2.size();
    int o=arr3.size();
    List<Integer> result=new ArrayList<>();
    Set<Integer> seen=new HashSet<>();
    while(i<m && j<n && k<o){
        if(arr1.get(i).equals(arr2.get(j)) && arr2.get(j).equals(arr3.get(k))){
            if(!seen.contains(arr1.get(i))){
                            result.add(arr1.get(i));
                            seen.add(arr1.get(i));

            }
            i++;j++;k++;
        }
        else if(arr1.get(i)<arr2.get(j)){
            i++;
        }
        else if(arr2.get(j)<arr3.get(k)){
            j++;
        }
        else{
            k++;
        }
    }
    if(result.isEmpty()){
        result.add(-1);
    }
    return result;
    
    }
}
```
