### Longest Common Prefix of Strings

##### [https://www.geeksforgeeks.org/problems/longest-common-prefix-in-an-array5129/1]
### c
```c
#include <stdio.h>
#include <string.h>
char* prefix(char arr[][100],int n){
    static char str[100];
    strcpy(str,arr[0]);
    for(int i=1;i<n;i++){
        int j=0;
        while(str[j]!='\0' && arr[i][j]!='\0' && str[j]==arr[i][j]){
            j++;
        }
        str[j]='\0';
        if(strlen(str)==0){
            return "-1";
        }
    }
    return str;
}

int main(){
    int n;
    scanf("%d",&n);
    char arr[n][100];
    for(int i=0;i<n;i++){
        scanf("%s",arr[i]);
    }
    printf("%s",prefix(arr,n));
}

```
### cpp
```cpp
class Solution {
  public:

    string longestCommonPrefix(vector<string> arr) {
        int n=arr.size();
    string str=arr[0];
    
    for(int i=1;i<n;i++){
        int j=0;
        while(j<str.length() && j<arr[i].length() && str[j]==arr[i][j]){
            j++;
        }
        str = str.substr(0, j); 
        if(str.empty()){
            return "-1";
        }
    }
    return str;



    }
};
```
### java
```java
class Solution {
    public String longestCommonPrefix(String arr[]) {
    

        int n=arr.length;
    String str=arr[0];
    
    for(int i=1;i<n;i++){
        int j=0;
        while(j<str.length() && j<arr[i].length() && str.charAt(j)==arr[i].charAt(j)){
            j++;
        }
        str = str.substring(0, j); 
        if(str.isEmpty()){
            return "-1";
        }
    }
    return str;



    }
}
```
