### count pairs with given sum
### c
```c
#include <stdio.h>

int main() {
    int n;
    int arr[]={4,5,12,4};
    n=sizeof(arr)/sizeof(arr[0]);
    int count=0;
    int k=2;
    for(int i=0;i<n-1;i++){
        for(int j=i+1;j<n;j++){
            if(arr[i]+arr[j]==k){
                count++;
            }
        }
    }
    printf("%d",count);

    return 0;
}
```
