### Queue

A Queue is a linear data structure that follows the **First In, First Out (FIFO)** principle. 

The element added first to the queue is the one that will be removed first.

## Application

- job scheduling
- bfs
- traffic management
- google form submission
- simulation  (customer service)

### operation

- **add**- Adds an element to the queue. It may throw an exception if the queue is full (in bounded queue implementations).
- **offer**- Adds an element to the queue. It differs from add() in that it doesn't throw an exception if the queue is full. Instead, it returns false in case of failure.
- **poll**- Removes and returns the element at the front of the queue.It returns null if the queue is empty (for Queue interfaces like LinkedList in Java).
- **remove**- Removes and returns the element at the front of the queue. It throws an exception (NoSuchElementException) if the queue is empty.
- **peek**- Returns (but does not remove) the element at the front of the queue.
- **element**- Returns (but does not remove) the element at the front of the queue. It throws an exception (NoSuchElementException) if the queue is empty.
- **isEmpty**- Checks if the queue is empty.
- **size**-Returns the number of elements in the queue.
- **clear**- Clears all elements from the queue, making it empty.
- **contains**- Checks if the queue contains a specific element.


**1.first non-repeating character**

leetcode-387

```java
class Solution {
    public int firstUniqChar(String s) {
        HashMap<Character,Integer> map=new HashMap<>();
        Queue<Character> q=new LinkedList<>();

        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            if(map.containsKey(ch)){
                int count=map.get(ch);
                count++;
                map.put(ch,count);
               
            }
            else {
                map.put(ch,1);
                q.add(ch);
            }
        }
        
       while(!q.isEmpty()){
        char firstChar=q.poll();
        int count=map.get(firstChar);
        if(count==1)
        return s.indexOf(firstChar);

       }
        return -1;
    }
}
```
**2.implement stack using queue**

leetcode-225

```java
class MyStack {

    public Queue<Integer>q1=new LinkedList<>();
    public Queue<Integer>q2=new LinkedList<>();


    public MyStack() {
        
    }
    
    public void push(int x) {
        q1.add(x);
        
    }
    
    public int pop() {
        while(q1.size()>1){
            q2.add(q1.poll());
        }
                    int topVar=q1.poll();
                   
                    Queue<Integer>temp=q2;
                    q2=q1;
                    q1=temp;
                    return topVar;


        
    }
    
    public int top() {
        while(q1.size()>1){
            q2.add(q1.poll());
        }
                    int topVar=q1.poll();
                    q2.add(topVar);
                    Queue<Integer>temp=q2;
                    q2=q1;
                    q1=temp;
                    return topVar;


        
    }
    
    public boolean empty() {
        return q1.isEmpty();
        
    }
}

/**
 * Your MyStack object will be instantiated and called as such:
 * MyStack obj = new MyStack();
 * obj.push(x);
 * int param_2 = obj.pop();
 * int param_3 = obj.top();
 * boolean param_4 = obj.empty();
 */
```
**3.petrol pump or gas station**
**4.LRU cache**
