### Java Arraylist
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-arraylist/submissions/code/1381744148]
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        
        
        ArrayList<ArrayList<Integer>> arr = new ArrayList<>();
        
        for (int i = 0; i < n; i++) {
            int d = s.nextInt();
            ArrayList<Integer> temp = new ArrayList<>();
            for (int j = 0; j < d; j++) {
                temp.add(s.nextInt());
            }
            arr.add(temp);
        }
        
        int q = s.nextInt();
        for (int i = 0; i < q; i++) {
            int x = s.nextInt();
            int y = s.nextInt();
            
            if (x > 0 && x <= n && y > 0 && y <= arr.get(x - 1).size()) {
                System.out.println(arr.get(x - 1).get(y - 1));
            } else {
                System.out.println("ERROR!");
            }
        }
        s.close();
    }
}

```
### Java 2D Array
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-2d-array/submissions/code/1381744324]
```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        
        int[][] arr = new int[6][6];
        
        for (int i = 0; i < 6; i++) {
            String[] arrRowTempItems = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");
            for (int j = 0; j < 6; j++) {
                arr[i][j] = Integer.parseInt(arrRowTempItems[j]);
            }
        }
        bufferedReader.close();
        
        int maxSum = Integer.MIN_VALUE;
        
        for (int i = 1; i < 5; i++) {
            for (int j = 1; j < 5; j++) {
                int currentSum = arr[i-1][j-1] + arr[i-1][j] + arr[i-1][j+1]  // top row
                              + arr[i][j]                                 // middle element
                              + arr[i+1][j-1] + arr[i+1][j] + arr[i+1][j+1]; // bottom row
                
                if (currentSum > maxSum) {
                    maxSum = currentSum;
                }
            }
        }
        
        System.out.println(maxSum);
    }
}

```
### Java Subarray
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-negative-subarray/submissions/code/1381744448]
```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int n = scanner.nextInt();
        
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }
        
        int count = 0;
        
        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = i; j < n; j++) {
                sum += arr[j];
                
                if (sum < 0) {
                    count++;
                }
            }
        }
        
        System.out.println(count);
        
        scanner.close();
    }
}

```
### java list
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-list/submissions/code/1381744769]
```java
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int n = scanner.nextInt();
        ArrayList<Integer> list = new ArrayList<>();

        for (int i = 0; i < n; i++) {
            list.add(scanner.nextInt());
        }

        int q = scanner.nextInt();

        for (int i = 0; i < q; i++) {
            String operation = scanner.next();

            if (operation.equals("Insert")) {
                int index = scanner.nextInt();
                int value = scanner.nextInt();
                list.add(index, value);
            } else if (operation.equals("Delete")) {
                int index = scanner.nextInt();
                list.remove(index);
            }
        }

        for (int num : list) {
            System.out.print(num + " ");
        }
        scanner.close();
    }
}

```
### java map
##### [https://www.hackerrank.com/contests/java-test5/challenges/phone-book/submissions/code/1381745100]
```java
import java.util.*;
import java.io.*;

class Solution {
    public static void main(String []argh) {
        Scanner in = new Scanner(System.in);

        int n = in.nextInt();
        in.nextLine(); // Consume the remaining newline

        HashMap<String, Integer> phoneBook = new HashMap<>();

        for(int i = 0; i < n; i++) {
            String name = in.nextLine(); 
            int phone = in.nextInt(); 
            in.nextLine(); 
            phoneBook.put(name, phone); 
        }

        while(in.hasNext()) {
            String s = in.nextLine();
            if(phoneBook.containsKey(s)) {
                System.out.println(s + "=" + phoneBook.get(s));
            } else {
                System.out.println("Not found");
            }
        }

        in.close();
    }
}

```
### java stack
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-stack/submissions/code/1381745175]
```java
import java.util.*;

class Solution {

    public static void main(String []argh) {
        Scanner sc = new Scanner(System.in);
        
        while (sc.hasNext()) {
            String input = sc.next();
            System.out.println(isBalanced(input));
        }
        
        sc.close();
    }

    public static boolean isBalanced(String input) {
        Stack<Character> stack = new Stack<>();

        for (char ch : input.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (stack.isEmpty()) {
                    return false;
                }
                char last = stack.pop();
                if (!isMatchingPair(last, ch)) {
                    return false;
                }
            }
        }
        
        return stack.isEmpty();
    }

    public static boolean isMatchingPair(char open, char close) {
        return (open == '(' && close == ')') ||
               (open == '{' && close == '}') ||
               (open == '[' && close == ']');
    }
}

```
### java hashset
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-hashset/submissions/code/1381745379]
```java


        HashSet<String> uniquePairs = new HashSet<>();
 
        for (int i = 0; i < t; i++) {
            String pair = pair_left[i] + " " + pair_right[i];

            uniquePairs.add(pair);

            System.out.println(uniquePairs.size());
        }

        s.close();
    

```
### java generics
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-generics/submissions/code/1381745507]
```java
class Printer
{
    public <T> void printArray(T[] array) {
        for (T element : array) {
            System.out.println(element);
        }
    }

 
}
```
### java comparator
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-comparator]
```java
// Write your Checker class here
class Checker implements Comparator<Player> {
    @Override
    public int compare(Player a, Player b) {
        if (a.score == b.score) {
            return a.name.compareTo(b.name); 
        } else {
            return b.score - a.score; 
        }
    }
}

```
### java bitset
##### [https://www.hackerrank.com/contests/java-test5/challenges/java-bitset/submissions/code/1381746129]
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int m = in.nextInt();
        
        BitSet bitset1 = new BitSet(n);
        BitSet bitset2 = new BitSet(n);
        
        for (int i = 0; i < m; i++) {
            String operation = in.next();
            int index1 = in.nextInt();
            int index2 = in.nextInt();
            
            switch (operation) {
                case "AND":
                    if (index1 == 1 && index2 == 2) {
                        bitset1.and(bitset2);
                    } else if (index1 == 2 && index2 == 1) {
                        bitset2.and(bitset1);
                    }
                    break;
                case "OR":
                    if (index1 == 1 && index2 == 2) {
                        bitset1.or(bitset2);
                    } else if (index1 == 2 && index2 == 1) {
                        bitset2.or(bitset1);
                    }
                    break;
                case "XOR":
                    if (index1 == 1 && index2 == 2) {
                        bitset1.xor(bitset2);
                    } else if (index1 == 2 && index2 == 1) {
                        bitset2.xor(bitset1);
                    }
                    break;
                case "FLIP":
                    if (index1 == 1) {
                        bitset1.flip(index2);
                    } else if (index1 == 2) {
                        bitset2.flip(index2);
                    }
                    break;
                case "SET":
                    if (index1 == 1) {
                        bitset1.set(index2);
                    } else if (index1 == 2) {
                        bitset2.set(index2);
                    }
                    break;
            }
            
            System.out.println(bitset1.cardinality() + " " + bitset2.cardinality());
        }
    }
}

```
