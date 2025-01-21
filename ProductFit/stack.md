## Stack

A stack is a **linear** data structure that follows the **Last In, First Out (LIFO)** principle. 

Last item added to the stack is the first item to be removed. 

### operations

* **Push**: Add an element to the top of the stack. 

* **Pop**: Remove the top element of the stack.

* **Peek/Top**: Retrieve the top element without removing it.

* **isEmpty**: Check if the stack is empty.
  
* **Size**: Get the current number of elements in the stack.

* **Search**: Finds the position of an element in the stack (1-based index from the top). Returns -1 if the element is not present.

* **Clear**: Removes all elements from the stack, leaving it empty.

* **Contains**: Checks if a specific element exists in the stack. Returns true if the element is found, otherwise false.





### Application
* function calls
* undo/redo operations
* syntax parsing
* backtracking
* browser navigation
  

**1.valid parenthesis**

leetcode-20


```java
class Solution {
    public boolean isValid(String s) {
         Stack<Character> st=new Stack<>();
        if(s.charAt(0)==')' || s.charAt(0)==']' || s.charAt(0)=='}'){
                return false;
            }

        for(int i=0;i<s.length();i++){
            if(s.length()==0){
                return true;
            }
            
            char currChar=s.charAt(i);
            if(currChar=='(' || currChar=='[' || currChar=='{'){
                st.push(currChar);
            }
            else if(st.isEmpty() && (currChar==')' || currChar==']' || currChar=='}')){
                return false;
            }
            else{
                char topChar=st.peek();
                if(topChar=='(' && currChar==')'){
                    st.pop();
                }
                else if(topChar=='[' && currChar==']'){
                    st.pop();
                }
                else if(topChar=='{' && currChar=='}'){
                    st.pop();
                }
                else{
                    return false;
                }
            }
        }

        if(!st.isEmpty()){
            return false;
        }
        return true;


        
    }
}

```
**2.min stack**

leetcode-155


```java
class MinStack {
    public Stack<Integer>stack=new Stack<>();
    public Stack<Integer>minStack=new Stack<>();

    public MinStack() {
        

        
    }
    
    public void push(int val) {
        stack.push(val);
        if(minStack.isEmpty() || minStack.peek()>=val){
            minStack.push(val);
        }
        
    }
    
    public void pop() {
        int a=minStack.peek();
        if(stack.pop()==a){
            minStack.pop();
        }
    
        
    }
    
    public int top() {
        return stack.peek();
        
    }
    
    public int getMin() {
        return minStack.peek();
        
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(val);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */
```
**3.Evaluate Reverse Polish Notation**

leetcode-150

```java

class Solution {
    public int evalRPN(String[] tokens) {
        Stack<Integer> fill=new Stack<>();

        for(int i=0;i<tokens.length;i++){
            String s=tokens[i];
            if(isNumber(s)){
                fill.push(Integer.parseInt(s));

            }
            else{
                int number1=fill.pop();
                int number2=fill.pop();
                int temp= 0;

                switch (s){
                    case "+":
                    temp=number1 + number2;
                    break;
                    case "-":
                    temp=number2 - number1;
                    break;
                    case "*":
                    temp=number1*number2;
                    break;
                    case "/":
                    temp=number2/number1;
                    break;
                }
                fill.push(temp);
                
            }
        }
        return fill.peek();
        
    }
     private boolean isNumber(String s) {
        try {
            Integer.parseInt(s);
            return true;
        } catch (NumberFormatException e) {
            return false;
        }
    }
}
```
**4.largest rectangle in histogram**

leetcode-84

```java
-----two pointer method gives time limit exceed--------

class Solution {
    public int largestRectangleArea(int[] heights) {
        int n=heights.length;
        int left=0;int right=n-1;
        int max=0;

        while(left<=right){
            int width=right-left;

            int min=Integer.min(heights[left],heights[right]);
            int area=width*min;
            if(area>max){
                max=area    ;
            }
            if(heights[left]<heights[right]){
                left++;
            }
            else if(heights[right]<heights[left]){
                right--;
            }

        }
        return max;
        
    }
}
```

```java
--------using stack----------
class Solution {
    public int largestRectangleArea(int[] heights) {
        Stack<Integer> stack = new Stack<>();
        int maxArea = 0;
        int index = 0;
        
        while (index < heights.length) {
            if (stack.isEmpty() || heights[stack.peek()] <= heights[index]) {
                stack.push(index++);
            } else {
                int topOfStack = stack.pop();
                int area = heights[topOfStack] * (stack.isEmpty() ? index : index - stack.peek() - 1);
                maxArea = Math.max(maxArea, area);
            }
        }
        
        while (!stack.isEmpty()) {
            int topOfStack = stack.pop();
            int area = heights[topOfStack] * (stack.isEmpty() ? index : index - stack.peek() - 1);
            maxArea = Math.max(maxArea, area);
        }
        
        return maxArea;
    }
}

```
