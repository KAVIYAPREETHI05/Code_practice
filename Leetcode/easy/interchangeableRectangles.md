### 2001. Number of Pairs of Interchangeable Rectangles

Time limit exceed
```java
class Solution {
    public long interchangeableRectangles(int[][] rect) {
        int m=rect.length;
        int n=rect[0].length;
        int count=0;
        for(int i=0;i<m;i++){
            double val1=(double)rect[i][0]/rect[i][1];
            for(int j=i+1;j<m;j++){
                double val2=(double)rect[j][0]/rect[j][1];               
                if(val1==val2){
                    count++;
                }
            }
        }
       return count; 
    }
}
```
``Time complexity=O(n);``
```java
class Solution {
    public long interchangeableRectangles(int[][] rect) {
       int n=rect.length;
       long count=0;
       Map<Double,Integer> s=new HashMap<>();
       for(int i=0;i<n;i++){
        double ratio=(double) rect[i][0]/rect[i][1];
        count+=s.getOrDefault(ratio,0);
        s.put(ratio,s.getOrDefault(ratio,0)+1);


       }
       return count; 
    }
}
```
