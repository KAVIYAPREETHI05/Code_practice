## HashSet

A HashSet is a collection in Java that implements the Set interface, which does not allow duplicate elements. 

In a HashSet, the elements are unordered, meaning there is no guarantee of the order in which elements will be stored.

### operations

- **add**- Adds the specified element to the set if it is not already present. If the element already exists, it will not be added (no duplicates).
- **remove**- Removes the specified element from the set. If the element is not present, it does nothing.
- **contains**- Checks if the set contains the specified element.
- **size**- Returns the number of elements in the set.
- **isEmpty**- Checks if the set is empty.
- **clear**- Removes all elements from the set.

### Applications

- removing duplicates
- set operations
- fast lookup
- tracking unique elements



**1.First Unique Element**

leetcode -387

```java
class Solution {
    public int firstUniqChar(String s) {
        HashSet<Character> seenOnce=new HashSet<>();
        HashSet<Character> seenMore=new HashSet<>();
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            if(seenOnce.contains(ch)){
                seenOnce.remove(ch);
                seenMore.add(ch);
            }
            else if(!seenMore.contains(ch)){
                seenOnce.add(ch);
            }
        }
        
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            if(seenOnce.contains(ch)){
                return i;
            }
           
        }
        return -1;
    }
}
```

**2.Set Matrics zeroes**

leetcode-73

```java
class Solution {
    public void setZeroes(int[][] matrix) {
        HashSet<Integer> rowSet=new HashSet<>();
        HashSet<Integer>colSet=new HashSet<>();

        for(int i=0;i<matrix.length;i++){
            for(int j=0;j<matrix[0].length;j++){
                if(matrix[i][j]==0){
                    rowSet.add(i);
                    colSet.add(j);
                }
            }
        }
        for(int i=0;i<matrix.length;i++){
            for(int j=0;j<matrix[0].length;j++){
                if(rowSet.contains(i) || colSet.contains(j)){
                    matrix[i][j]=0;
                }
            }
        }


        
    }
}
```
