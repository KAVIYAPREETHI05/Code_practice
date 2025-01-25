## LinkedList

A linked list is a linear data structure where elements, called nodes, are linked using pointers.

Unlike arrays, linked lists do not store elements in contiguous memory locations. Instead, each node points to the next, creating a chain-like structure.

Each node contains two parts

1.**Data**: The actual data stored in the node.
2.**Pointer (next)**: A reference (or pointer) to the next node in the sequence.

### Types of Linked Lists
- Singly Linked List:

  - Each node points to the next node.
  - Traversal is unidirectional (only forward).
- Doubly Linked List:

  - Each node has two pointers: one to the next node and one to the previous node.
  - Traversal is bidirectional.
- Circular Linked List:

  - The last node points to the first node, forming a circular structure.
  - Can be singly or doubly linked.

### Applications

- Undo functionality in text editors.
- Browser history (forward/back navigation).
- Music playlists (next/previous track).
- Round-robin scheduling.
- Multiplayer gaming (player turns).

### Operations

- `add(value)`Adds value to the end of the list.
- `addFirst(value)`Adds value to the beginning of the list.
- `addLast(value)`Adds value to the end of the list.
- `remove(index)`Removes the element at the specified index.
- `removeFirst()`Removes the first element of the list.
- `removeLast()`Removes the last element of the list.
- `getFirst()`Retrieves the first element of the list.
- `getLast()`Retrieves the last element of the list.
- `size()`Returns the number of elements in the list.
- `contains(value)`Checks if value exists in the list.

**add elements in linked list**

```java
import java.util.Scanner;
import java.util.LinkedList;


public class Main{
    public static void main(String[] args){
        LinkedList list=new LinkedList();
        Scanner scan=new Scanner(System.in);
        
        int totalNode=scan.nextInt();
        
        for(int i=0;i<totalNode;i++){
            int value=scan.nextInt();
            list.add(value);
        }
        
        for(int i=0;i<totalNode;i++){
            System.out.println(list.get(i));
        }
        
    }
}
```


**traverse a linked list**

```java
/* Node is defined as
class Node {
    int data;
    Node next;
    Node(int x) {
        data = x;
        next = null;
    }
}*/


class Solution {
    // Function to display the elements of a linked list in same line
    void printList(Node head) {
        while(head!=null){
            System.out.print(head.data+" ");
            head=head.next;
        }
    }
}
```

**search in linked list**

```java
class Solution {
    static boolean searchKey(int n, Node head, int key) {
     
        
        while(head!=null){
            if(head.data==key){
                return true;
            }
            head=head.next;
        }
        return false;
    }
}
```

**insert element at end**

```java
class Solution {
    Node insertAtEnd(Node head, int x) {
        Node newNode=new Node(x);
        if(head==null){
            return newNode;
        }
        Node temp=head;
        while(temp.next!=null){
            temp=temp.next;
        }
        temp.next=newNode;
       
        return head;
    }
}
```

**delete first element in ll**
```java
import java.util.Scanner;

class Node{
    int data;
    Node next;
    public  Node(int data){
        this.data=data;
        this.next=null;
    }
}


public class Main
{
    public static void deleteNode(Node head){
        head=head.next;
        Node temp=head;
        
        
        while(temp!=null){
            System.out.println(temp.data);
            temp=temp.next;
        }
    }
    
	public static void main(String[] args) {
	    Scanner scan=new Scanner(System.in);
	    int size=scan.nextInt();
	    
	    Node head=null;
	    Node tail=null;
	    
	    for(int i=0;i<size;i++){
	        int value=scan.nextInt();
	        Node newNode=new Node(value);
	        
	        if(head==null){
	            head=newNode;
	            tail=newNode;
	        }
	        else{
	            tail.next=newNode;
	            tail=newNode;
	            
	        }
	    }
	    
	    deleteNode(head);
	}
}
```

**delete last element in ll**

```java
class Solution {
    Node deleteLastNode(Node head) {
        if (head == null || head.next == null) {
            return null;
        }

        Node temp = head;
        while (temp.next != null && temp.next.next != null) {
            temp = temp.next;
        }

        temp.next = null;

        return head;
    }
}
```
**Reverse Linked List**

leetcode-206

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {

        ListNode prev=null;
        ListNode curr=head;
        ListNode nextNode=new ListNode();

        while(curr!=null){
            nextNode=curr.next;
            curr.next=prev;
            prev=curr;
            curr=nextNode;

        }
     
        return prev;
        
    }
}
```
**Add 1 to linked list**
```java
class Solution {
    public Node addOne(Node head) {
        // code here.
        if(head==null){
            return new Node(1);
        }
        
        head=reversedLinkedList(head);
        Node current=head;
        int carry=1;
        Node prev=null;
        
        while(current!=null){
            int sum=current.data+carry;
            current.data=sum%10;
            carry=sum/10;
            prev=current;
            current=current.next;
        }
        if(carry>0){
            prev.next=new Node(carry);
        }
        head=reversedLinkedList(head);
        return head;
    }
    Node reversedLinkedList(Node head){
    Node prev=null;
    while(head!=null){
        Node newNode=head.next;
        head.next=prev;
        prev=head;
        head=newNode;
    }
    return prev;
}

}
```
**detect cycle**
```java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public boolean hasCycle(ListNode head) {
       
        ListNode temp=head;
        Stack<ListNode> s=new Stack<>();

        while(temp!=null){
            if(s.contains(temp)){
                return true;
            }            
            s.add(temp);
           temp=temp.next;
            
           
        }
         return false;
    }
}
```
**merge k two sorted list**
**find intersection**
```java
**add two num**
**remove kth from end**
**rearrange nodes**
**palindrom linked list**
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public boolean isPalindrome(ListNode head) {
        if(head==null || head.next==null){
            return true;
        }
        ListNode slow=head;ListNode fast=head;

        while(fast!=null && fast.next!=null){
            slow=slow.next;
            fast=fast.next.next;
        }

        ListNode curr=slow;
        ListNode prev=null;

        while(curr!=null){
            ListNode newNode=curr.next;
            curr.next=prev;
            prev=curr;
            curr=newNode;
        }

          ListNode firstHalf=head; ListNode secondHalf=prev;

       while(secondHalf!=null){
        if(firstHalf.val!=secondHalf.val){
            return false;
        }
        firstHalf=firstHalf.next;
        secondHalf=secondHalf.next;
       }
       return true;
        
    }
}
```

---
---

**Finding middle element in a Linked list**

```java
class Solution {
        int getMiddle(Node head) {
            if(head==null || head.next==null){
                return head.data;
            }
           
            Node slow=head;
            Node fast=head;
            while(fast!=null && fast.next!=null){
                slow=slow.next;
                fast=fast.next.next;
            }
            
            
            return slow.data;
            
        }
    }
```

**Reverse a Linked list $**

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {

        ListNode prev=null;
        ListNode curr=head;
        ListNode nextNode=new ListNode();

        while(curr!=null){
            nextNode=curr.next;
            curr.next=prev;
            prev=curr;
            curr=nextNode;

        }
     
        return prev;
        
    }
}
```
**Rotate a Linked List $**

leetcode-61

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode rotateRight(ListNode head, int k) {
           ListNode temp=new ListNode();
        if(k==0 || head==null || head.next==null){
            return head;
        }
        temp=head;
        int length=0;
        while(temp!=null){
            length++;
            temp=temp.next;

        }


        for(int i=0;i<k%length;i++){
            ListNode newNode=new ListNode();
           
              ListNode prev=null;

temp=head;
            while(temp.next.next!=null){
                temp=temp.next;
            }
          newNode=temp.next;
          temp.next=prev;

          newNode.next=head;
          head=newNode;

        }       

            return head;
        
    }
}
```
**Reverse a Linked List in groups of given size**
**Intersection point in Y shaped Linked lists**
**Detect Loop in Linked list**
**Remove loop in Linked List**
**n’th node from end of Linked list**
**Flattening a Linked List**
**Merge two sorted Linked lists**
**Pairwise swap of a Linked list**
**Add two numbers represented by Linked lists**
**Check if Linked List is Palindrome**
**Implement Queue using Linked List**
**Implement Stack using Linked List**
**Given a Linked list of 0s, 1s and 2s, sort it**
**Delete without head pointer**


## DOUBLYLINKED LIST

**traversing doubly linked list**

```java

class Node{
    int data;
    Node prev;
    Node next;
    
    public Node(int value){
        this.data=value;
        this.next=null;
        this.prev=null;
    }
}

class DoublyLinkedList{
Node head=null;
Node tail=null;
    public void addToFront(int data){
        Node newNode=new Node(data);
        if(head==null){
            head=tail=newNode;
        }
        else{
            head.prev=newNode;
            newNode.next=head;
            head=newNode;
            
        }
    }
    
    public void addToLast(int data){
        Node newNode=new Node(data);
        if(head==null){
            head=tail=newNode;
        }
        else{
            tail.next=newNode;
            newNode.prev=tail;
            tail=newNode;
            
        }
    }
    
    public void displayForward(){
        Node current=head;
        while(current!=null){
            System.out.print(current.data+" ");
            current=current.next;
        }
        System.out.println();
    }
    public void displayBackward(){
        Node current=tail;
        while(current!=null){
            System.out.print(current.data+" ");
            current=current.prev;
        }
    }
    
}

public class Main{
    public static void main(String[] args){
        
        DoublyLinkedList dll=new DoublyLinkedList();
        
        dll.addToFront(3);
        dll.addToFront(2);
        dll.addToFront(1);
        dll.addToLast(4);
        dll.addToLast(5);
        dll.addToLast(6);        
        
        dll.displayForward();
        dll.displayBackward();        
               
    }
}
```





