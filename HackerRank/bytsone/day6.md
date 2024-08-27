### Java 1D Array 
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-1d-array/submissions/code/1381830009]
```java
import java.util.*;

public class Solution {

    public static boolean canWin(int leap, int[] game, int index) {
        // Base cases
        if (index >= game.length) {
            return true; // We have moved beyond the end of the array
        }
        if (index < 0 || game[index] == 1) {
            return false; // Out of bounds or hit a 1
        }

        // Mark this cell as visited by setting it to 1
        game[index] = 1;

        // Recursive checks
        return canWin(leap, game, index + leap) ||
               canWin(leap, game, index + 1) ||
               canWin(leap, game, index - 1);
    }

    public static boolean canWin(int leap, int[] game) {
        return canWin(leap, game, 0); // Start from index 0
    }

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int q = scan.nextInt();
        while (q-- > 0) {
            int n = scan.nextInt();
            int leap = scan.nextInt();
            
            int[] game = new int[n];
            for (int i = 0; i < n; i++) {
                game[i] = scan.nextInt();
            }

            System.out.println(canWin(leap, game) ? "YES" : "NO");
        }
        scan.close();
    }
}

```

### Java 2D Array 
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-2d-array/submissions/code/1381830155]
```java
import java.io.*;
import java.util.*;

public class Solution {
    
    // Function to calculate the sum of an hourglass
    public static int hourglassSum(List<List<Integer>> arr, int row, int col) {
        return arr.get(row).get(col)     + arr.get(row).get(col + 1)     + arr.get(row).get(col + 2)
             + arr.get(row + 1).get(col + 1)
        + arr.get(row + 2).get(col)     + arr.get(row + 2).get(col + 1)     + arr.get(row + 2).get(col + 2);
    }

    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        List<List<Integer>> arr = new ArrayList<>();

        // Reading the 6x6 matrix
        for (int i = 0; i < 6; i++) {
            String[] arrRowTempItems = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");
            List<Integer> arrRowItems = new ArrayList<>();
            for (int j = 0; j < 6; j++) {
                int arrItem = Integer.parseInt(arrRowTempItems[j]);
                arrRowItems.add(arrItem);
            }
            arr.add(arrRowItems);
        }

        bufferedReader.close();

        // Initialize the maximum hourglass sum to a very small value
        int maxSum = Integer.MIN_VALUE;

        // Calculate the hourglass sum for each possible hourglass
        for (int i = 0; i < 4; i++) { // 4 possible hourglasses in row
            for (int j = 0; j < 4; j++) { // 4 possible hourglasses in column
                int sum = hourglassSum(arr, i, j);
                if (sum > maxSum) {
                    maxSum = sum;
                }
            }
        }

        // Print the maximum hourglass sum
        System.out.println(maxSum);
    }
}

```
### java substring
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-negative-subarray/submissions/code/1381830321]
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        // Read the length of the array
        int n = Integer.parseInt(bufferedReader.readLine().trim());

        // Read the array elements
        String[] arrTemp = bufferedReader.readLine().trim().split(" ");
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = Integer.parseInt(arrTemp[i]);
        }

        bufferedReader.close();

        // Count the number of subarrays with negative sum
        int negativeSumCount = 0;

        // Generate all subarrays
        for (int i = 0; i < n; i++) {
            int currentSum = 0;
            for (int j = i; j < n; j++) {
                currentSum += arr[j];
                if (currentSum < 0) {
                    negativeSumCount++;
                }
            }
        }

        // Print the result
        System.out.println(negativeSumCount);
    }
}

```
### java ArrayList
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-arraylist/submissions/code/1381831019]
```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Reading the number of lines
        int n = scanner.nextInt();
        List<List<Integer>> listOfLists = new ArrayList<>();
        
        // Reading each line and storing them in listOfLists
        for (int i = 0; i < n; i++) {
            int d = scanner.nextInt();
            List<Integer> list = new ArrayList<>();
            for (int j = 0; j < d; j++) {
                list.add(scanner.nextInt());
            }
            listOfLists.add(list);
        }
        
        // Reading the number of queries
        int q = scanner.nextInt();
        
        // Handling each query
        for (int i = 0; i < q; i++) {
            int x = scanner.nextInt();
            int y = scanner.nextInt();
            
            // Checking if the line and position are valid
            if (x > 0 && x <= listOfLists.size() && y > 0 && y <= listOfLists.get(x-1).size()) {
                System.out.println(listOfLists.get(x-1).get(y-1));
            } else {
                System.out.println("ERROR!");
            }
        }
        
        scanner.close();
    }
}
```
### java List
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-list/submissions/code/1381831466]
```java
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Read the initial number of elements in the list
        int n = scanner.nextInt();
        
        // Initialize the list and populate it with input integers
        List<Integer> list = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            list.add(scanner.nextInt());
        }
        
        // Read the number of queries
        int q = scanner.nextInt();
        
        // Process each query
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
        
        // Print the modified list
        for (int value : list) {
            System.out.print(value + " ");
        }
        
        scanner.close();
    }
}
```
### java map
##### [https://www.hackerrank.com/contests/java-test6/challenges/phone-book/submissions/code/1381831621]
```java
import java.util.*;
import java.io.*;

class Solution {
    public static void main(String []argh) {
        Scanner in = new Scanner(System.in);
        
        // Initialize the phone book
        Map<String, Integer> phoneBook = new HashMap<>();
        
        // Read the number of entries
        int n = in.nextInt();
        in.nextLine(); // Consume the newline character
        
        // Populate the phone book
        for (int i = 0; i < n; i++) {
            String name = in.nextLine();
            int phone = in.nextInt();
            in.nextLine(); // Consume the newline character
            phoneBook.put(name, phone);
        }
        
        // Process the queries until the end of input
        while (in.hasNext()) {
            String queryName = in.nextLine();
            if (phoneBook.containsKey(queryName)) {
                System.out.println(queryName + "=" + phoneBook.get(queryName));
            } else {
                System.out.println("Not found");
            }
        }
        
        in.close();
    }
}
```
### java stack
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-stack/submissions/code/1381831706]
```java
import java.util.*;

class Solution {
    public static void main(String []argh) {
        Scanner sc = new Scanner(System.in);
        
        while (sc.hasNext()) {
            String input = sc.next();
            System.out.println(isBalanced(input));
        }
    }
    
    public static boolean isBalanced(String s) {
        Stack<Character> stack = new Stack<>();
        
        for (char ch : s.toCharArray()) {
            // If it's an opening bracket, push to stack
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            }
            // If it's a closing bracket, check if it matches the top of the stack
            else if (ch == ')' || ch == '}' || ch == ']') {
                if (stack.isEmpty()) {
                    return false; // No matching opening bracket
                }
                
                char top = stack.pop();
                if ((ch == ')' && top != '(') || 
                    (ch == '}' && top != '{') || 
                    (ch == ']' && top != '[')) {
                    return false; // Mismatched pair
                }
            }
        }
        
        // If the stack is empty, all brackets were matched correctly
        return stack.isEmpty();
    }
}
```
### java generics
##### [https://www.hackerrank.com/contests/java-test6/challenges/java-generics/submissions/code/1381832015]
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
