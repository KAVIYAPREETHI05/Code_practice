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

2D to 1D
```java
class Solution {
    public int[] convert2DTo1D(int[][] matrix) {
        int m = matrix.length; 
        int n = matrix[0].length; 
      
        int[] oneDArray = new int[m * n];
        int index = 0;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                oneDArray[index++] = matrix[i][j];
            }
        }
        
        return oneDArray;
    }
}
```
