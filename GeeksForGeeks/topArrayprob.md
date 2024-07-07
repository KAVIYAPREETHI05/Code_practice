### Reverse a String
###### [https://www.geeksforgeeks.org/problems/reverse-a-string/1]
## c
```c
char* reverseWord(char* str) {
    int n=strlen(str);
    
    for(int i=0;i<n/2;i++){
        int temp=str[i];
        str[i]=str[n-i-1];
        str[n-i-1]=temp;
    }
    return str;
}
```
## cpp
```cpp
class Solution
{
    public:
    string reverseWord(string str)
    {
        reverse(str.begin(),str.end());
        return str;
 
    }
};
```
## java
```java
class Reverse
{
    // Complete the function
    // str: input string
    public static String reverseWord(String str)
    {
        StringBuilder reversed=new StringBuilder(str);
        reversed.reverse();
        String reversedstring=reversed.toString();
        return reversedstring;
        // Reverse the string str
    }
}
```
