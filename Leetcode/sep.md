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
## Day-3
### Sum of Digits of String After Convert
```java
class Solution {
    public int getLucky(String s, int k) {
       StringBuilder numString=new StringBuilder();
       for(char c:s.toCharArray()){
        int number=c-'a'+1;
        numString.append(number);
       }
       String currentString=numString.toString();
       int result=0;
       for(int i=0;i<k;i++){
        result=0;
        for(char digit:currentString.toCharArray()){
            result+=digit-'0';
        }
        currentString=Integer.toString(result);
       }
       return result;
    }
}
```

