### separate Digits in array
## c
```c
#include<stdio.h>

int main(){
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }int j=0;int brr[1000];
    for(int i=0;i<n;i++){
        int num=arr[i];
        if(num==0){
            brr[j++]=num;
        }
        else if(num<0){
            num=-num;
        }
        int digits[10];
        int digitcount=0;
        while(num!=0){
            int digit=num%10;
            digits[digitcount++]=digit;
            num/=10;
        }
        for(int i=digitcount-1;i>=0;i--){
            brr[j++]=digits[i];
        }
    }
    for(int i=0;i<j;i++){
        printf("%d ",brr[i]);
    }
}
```
## cpp
```cpp
class Solution {
public:
    vector<int> separateDigits(vector<int>& arr) {
        int n=arr.size();
        vector<int>brr;
    for(int i=0;i<n;i++){
        int num=arr[i];
        if(num==0){
            brr.push_back(0);
        }
        else if(num<0){
            num=-num;
        }
        int digits[10];
        int digitcount=0;
        while(num!=0){
            int digit=num%10;
            digits[digitcount++]=digit;
            num/=10;
        }
        for(int i=digitcount-1;i>=0;i--){
            brr.push_back(digits[i]);
        }
    }
  return brr;  
    }
};
```
### java
```java

