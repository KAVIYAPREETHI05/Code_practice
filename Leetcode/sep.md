## Day-1
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
## Day-2
### 1894. Find the Student that Will Replace the Chalk
```java
class Solution {
    public int chalkReplacer(int[] chalk, int k) {
        int n=chalk.length;
        long totalChalk = 0;
        for (int i = 0; i < n; i++) {
            totalChalk += chalk[i];
        }
        
        // Reduce k by full rounds of chalk use
        k %= totalChalk;
            for(int i=0;i<n;i++){
                if(k<chalk[i]){
                   return i; 
                }
                k=k-chalk[i];
            }

        
     return -1;   
    }
}
```
