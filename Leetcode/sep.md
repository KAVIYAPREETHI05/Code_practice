### 2022. Convert 1D Array Into 2D Array
```java
class Solution {
    public int[][] construct2DArray(int[] original, int m, int n) {
        int size=original.length;
         if (size != m * n) {
            return new int[0][0];  // Return an empty 2D array
        }
        int [][] matrix=new int [m][n];
        for(int i=0;i<size;i++){
            int row=i/n;
            int col=i%n;
            matrix[row][col]=original[i];
        }
        return matrix;
    }
}
```
