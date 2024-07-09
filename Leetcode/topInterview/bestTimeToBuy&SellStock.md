### 121. Best Time to Buy and Sell Stock
##### [https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/?envType=study-plan-v2&envId=top-interview-150]
## c
```c
int maxProfit(int* arr, int pricesSize) {
    if (pricesSize==0) return 0;
    int minprice=arr[0];
    int max=0;
    for(int i=1;i<pricesSize;i++){
        if(arr[i]<minprice){
            minprice=arr[i];
        }       
         else  if((arr[i]-minprice)>max){
                max=(arr[i]-minprice);
            }        
    }
    return max;
    
}
```
## cpp
```cpp
class Solution {
public:
    int maxProfit(vector<int>& arr) {
        int pricesSize=arr.size();
         if (pricesSize==0) return 0;
    int minprice=arr[0];
    int max=0;
    for(int i=1;i<pricesSize;i++){
        if(arr[i]<minprice){
            minprice=arr[i];
        }       
         else  if((arr[i]-minprice)>max){
                max=(arr[i]-minprice);
            }        
    }
    return max;
        
    }
};
```
## java
class Solution {
    public int maxProfit(int[] arr) {
        int pricesSize=arr.length;
         if (pricesSize==0) return 0;
    int minprice=arr[0];
    int max=0;
    for(int i=1;i<pricesSize;i++){
        if(arr[i]<minprice){
            minprice=arr[i];
        }       
         else  if((arr[i]-minprice)>max){
                max=(arr[i]-minprice);
            }        
    }
    return max;
        
    }
}
```
