### Reverse Words
##### [https://www.geeksforgeeks.org/problems/reverse-words-in-a-given-string5459/1]
### c
```c
#include <stdio.h>
#include<string.h>
int main() {
    char str[100];char reverse[100];
    fgets(str,sizeof(str),stdin);
    int n=strlen(str);
    if(str[n-1]=='\n'){
        str[n-1]='\0';
        n--;
    }
    int end=n-1;
    int index=0;
    for(int i=end;i>=0;i--){
        if(str[i]=='.'){
            int start=i+1;
            for(int j=start;j<=end;j++){
                reverse[index++]=str[start++];
            }
            end=i-1;
            reverse[index++]='.';
        }
    }int i=0;
    
        while(i<=end){
            reverse[index++]=str[i++];
           
        }
    
    reverse[index]='\0';
    printf("%s",reverse);

    return 0;
}
```
### cpp
```cpp

class Solution
{
    public:
    //Function to reverse words in a given string.
    string reverseWords(string S) 
    { 
     int n=S.length();
     string reverse;
    int end=n-1;
    int index=0;
    for(int i=end;i>=0;i--){
        if(S[i]=='.'){
            int start=i+1;
            for(int j=start;j<=end;j++){
                reverse[index++]=S[start++];
            }
            end=i-1;
            reverse[index++]='.';
        }
    }int i=0;
    
        while(i<=end){
            reverse[index++]=S[i];
            i++;
           
        }
    
    reverse[index]='\0';
    

    return reverse;
}
```
### java
```java
class Solution 
{
    //Function to reverse words in a given string.
    String reverseWords(String str)
    {
        int n=str.length();
    int end=n-1;
   String reverse="";
    for(int i=end;i>=0;i--){
        if(str.charAt(i)=='.'){
            int start=i+1;
            for(int j=start;j<=end;j++){
                reverse += str.charAt(start++);
            }
            end=i-1;
            reverse+='.';
        }
    }int i=0;
    
        while(i<=end){
            reverse+=str.charAt(i);
            i++;
           
        }
    
    
    

    return reverse;

    }
}
```
