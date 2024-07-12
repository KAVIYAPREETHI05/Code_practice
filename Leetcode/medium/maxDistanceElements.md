### Max distance between same elements

```c
#include <stdio.h>
#include <limits.h>

int maxDistance(int arr[], int n) {
    // Create an array to store the first occurrence index of each element
    int firstOccurrence[1000]; // Assuming the elements are in the range of 0-999
    for (int i = 0; i < 1000; i++) {
        firstOccurrence[i] = -1; // Initialize with -1
    }

    int maxDistance = 0;

    for (int i = 0; i < n; i++) {
        int element = arr[i];
        
        // If this is the first occurrence of the element
        if (firstOccurrence[element] == -1) {
            firstOccurrence[element] = i; // Store the index
        } else {
            // Calculate distance from the first occurrence to current index
            int distance = i - firstOccurrence[element];
            if (distance > maxDistance) {
                maxDistance = distance; // Update max distance if needed
            }
        }
    }

    return maxDistance;
}

int main() {
    int arr[] = {1, 1, 2, 2, 2, 1};
    int n = sizeof(arr) / sizeof(arr[0]);
    
    int result = maxDistance(arr, n);
    printf("Maximum distance: %d\n", result);
    
    return 0;
}

```
