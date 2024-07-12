### Arrange zeros after each element  in array	

## c
```c
#include<stdio.h>
int main(){
    int arr[]={1,2,0,3,0,0,4};
    int n=sizeof(arr)/sizeof(arr[0]);
    int zero[n];int z=0;
    int nonzero[n];int nonz=0;
    int brr[n];
    for(int i=0,j=0,k=0;i<n;i++){
        if(arr[i]==0){
            zero[j++]=arr[i];
            z++;
        }
        else{
            nonzero[k++]=arr[i];
            nonz++;
        }
    }
    for(int i=0,j=0;i<n;i++){
        brr[j++]=nonzero[i];
        if(i<z){
            brr[j++]=zero[i];
        }
    }
    for(int i=0;i<n;i++){
        printf("%d ",brr[i]);
    }
}
```
