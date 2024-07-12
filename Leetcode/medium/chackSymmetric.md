### Write a program to read elements in a matrix and check whether the given matrix is a symmetric matrix or not.
##c
```c
#include<stdio.h>
int checksymmetric(int arr[100][100],int n){
    
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(arr[i][j]!=arr[j][i]){
                return 0;
            }
        }
            }
    return 1;
}
int main(){
    int n;
    scanf("%d",&n);
    int arr[100][100];
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            scanf("%d",&arr[i][j]);
        }
    }
    if(checksymmetric(arr,n)){
        printf("given matrix is symmetric");
    }
    else{
        printf("given matrix is not symmetric");
    }
}
```
