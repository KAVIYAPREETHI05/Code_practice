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


**1.traverse a linked list**

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

**2.search in linked list**

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

**3.insert element at end**

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

**4.delete first element in ll**

**5.delete last element in ll**

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



