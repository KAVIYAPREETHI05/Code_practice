### 1508. Range Sum of Sorted Subarray Sums

### c
```c

#include <stdio.h>
#include<stdlib.h>

int main() {
    int arr[]={1,2,3,4};
    int n=sizeof(arr)/sizeof(arr[0]);
    int size=0;int left=1;int right=5;
    int max_size=n*(n+1)/2;
    int *temp=(int*) malloc (max_size * sizeof(int));
    for(int i=0;i<n;i++){
        int sum=0;
        for(int j=i;j<n;j++){
                sum+=arr[j];
                temp[size++]=sum;
         
        }
    }
    for(int i=0;i<size-1;i++){
        for(int j=i;j<size;j++){
            if(temp[i]>temp[j]){
                int temp_=temp[i];
                temp[i]=temp[j];
                temp[j]=temp_;
            }
        }
    }
    int value=0;
    for(int i=left-1;i<=right-1;i++){
        value+=temp[i];
    }
        printf("%d ",value);
        free(temp);

    return 0;
}
```

