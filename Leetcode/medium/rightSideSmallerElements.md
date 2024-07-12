### Count Smaller elements

## c
```c
#include <stdio.h>
#include <stdlib.h>

void constructLowerArray(int *arr, int n, int *answer) {
    // Initialize the answer array
    for (int i = 0; i < n; i++) {
        answer[i] = 0; // Start with zero counts
    }

    // Count the number of elements lower than each element
    for (int i = 0; i < n; i++) {
        int count = 0;
        for (int j = 0; j < n; j++) {
            if (arr[j] < arr[i]) {
                count++;
            }
        }
        answer[i] = count;
    }
}

int main() {
    int arr[] = {4, 5, 2, 10, 8};
    int n = sizeof(arr) / sizeof(arr[0]);
    int *answer = (int *)malloc(n * sizeof(int));

    constructLowerArray(arr, n, answer);

    printf("Lower Array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", answer[i]);
    }
    printf("\n");

    free(answer);
    return 0;
}

```
## cpp
```cpp
class Solution{
public:	
	vector<int> constructLowerArray(int *arr, int n) {
	    // code here
	    vector<int>answer(n,0);
	    for(int i=0;i<n-1;i++){
	        int count=0;
	        for(int j=i+1;j<n;j++){
	            if(arr[j]<arr[i]){
	                count++;
	            }
	        }
	        answer[i]=count;
	    }
	    
	    return answer;
	}
};
```
