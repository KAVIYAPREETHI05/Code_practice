### array Duplicates
##### [https://www.geeksforgeeks.org/problems/find-duplicates-in-an-array/1]
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
