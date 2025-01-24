## HashMap

A HashMap is a collection class in Java that implements the **Map** interface.

It allows you to store **key-value** pairs, where each key is unique, and it maps to exactly one value.

### Operations

- **put**- Inserts the specified key-value pair into the map. If the key already exists, the existing value is replaced with the new one.
- **get**- Retrieves the value associated with the given key.
- **remove**- Removes the key-value pair for the given key.
- **containsKey**- Checks if the map contains the specified key.
- **size**- Returns the number of key-value pairs in the map.
- **isEmpty**- Checks if the map is empty.
- **clear**- Removes all the key-value pairs from the map.

### Application

- caching
- counting frequency
- implementing dictionaries
- finding pairs or triplets
- storing unique elements
- mongodb

**1.two sum**

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map=new HashMap<>();

        for(int i=0;i<nums.length;i++){
            int complement=target-nums[i];
            if(map.containsKey(complement)){
                return new int[]{map.get(complement),i};
            }
            else{
                map.put(nums[i],i);
            }


        }
return new int[]{};
        
    }
}
```

**2.First Unique Char**

leetcode-387

```java
class Solution {
    public int firstUniqChar(String s) {
        HashMap<Character,Integer> hm=new HashMap<>();
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            hm.put(ch,hm.getOrDefault(ch,0)+1);
        }
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            if(hm.get(ch)==1){
                return i;
            }
           
        }
        return -1;
    }
}
```

---
---

**First element to occur k times**
**Find the element that appears once in sorted array**
**Number of pairs**
**Find all pairs with a given sum**
**Common elements**
**Find all four sum numbers**
**Count distinct elements in every window**
**Array Pair Sum Divisibility Problem**
**Longest consecutive subsequence**
**Array Subset of another array**
**Zero Sum Subarrays**
**Relative Sorting**
