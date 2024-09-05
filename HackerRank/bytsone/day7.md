### Print the Elements of a Linked List
```java
    // Complete the printLinkedList function below.

    /*
     * For your reference:
     *
     * SinglyLinkedListNode {
     *     int data;
     *     SinglyLinkedListNode next;
     * }
     *
     */
    static void printLinkedList(SinglyLinkedListNode head) {
        SinglyLinkedListNode temp=head;
         while(temp!=null){
             System.out.println(temp.data);
             temp=temp.next;
         }
    


    }
```
### Print in Reverse

```java
 public static void reversePrint(SinglyLinkedListNode llist) {
    // Write your code here
       if(llist==null){
           return;
       }
        reversePrint(llist.next);
        System.out.println(llist.data);

    }

```
### Reverse a linked list

```java
  public static SinglyLinkedListNode reverse(SinglyLinkedListNode head) {
    // Write your code here
        SinglyLinkedListNode temp=head;
        SinglyLinkedListNode prev=null;
        while(temp!=null){
            temp=head.next;
            head.next=prev;
            prev=head;
            head=temp;
        }
        return prev;

    }
```
### Compare two linked lists

```java
import java.util.Scanner;

class SinglyLinkedListNode {
    public int data;
    public SinglyLinkedListNode next;

    public SinglyLinkedListNode(int nodeData) {
        this.data = nodeData;
        this.next = null;
    }
}

class SinglyLinkedList {
    public SinglyLinkedListNode head;
    public SinglyLinkedListNode tail;

    public SinglyLinkedList() {
        this.head = null;
        this.tail = null;
    }

    public void insertNode(int nodeData) {
        SinglyLinkedListNode node = new SinglyLinkedListNode(nodeData);

        if (this.head == null) {
            this.head = node;
        } else {
            this.tail.next = node;
        }

        this.tail = node;
    }
}

public class LinkedListComparison {

    // Function to compare two linked lists
    public static int compareLists(SinglyLinkedListNode head1, SinglyLinkedListNode head2) {
        SinglyLinkedListNode temp1 = head1;
        SinglyLinkedListNode temp2 = head2;

        // Traverse both lists simultaneously
        while (temp1 != null && temp2 != null) {
            // Compare the data of corresponding nodes
            if (temp1.data != temp2.data) {
                return 0;
            }
            temp1 = temp1.next;
            temp2 = temp2.next;
        }

        // If both lists are exhausted, they are identical
        return (temp1 == null && temp2 == null) ? 1 : 0;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Get the number of test cases
        int testCases = scanner.nextInt();

        // Loop through each test case
        for (int t = 0; t < testCases; t++) {

            // Create the first linked list
            SinglyLinkedList list1 = new SinglyLinkedList();
            int n1 = scanner.nextInt();
            for (int i = 0; i < n1; i++) {
                int data = scanner.nextInt();
                list1.insertNode(data);
            }

            // Create the second linked list
            SinglyLinkedList list2 = new SinglyLinkedList();
            int n2 = scanner.nextInt();
            for (int i = 0; i < n2; i++) {
                int data = scanner.nextInt();
                list2.insertNode(data);
            }

            // Compare the two linked lists and store the result
            int result = compareLists(list1.head, list2.head);

            // Print the result for the current test case
            System.out.println(result);
        }

        scanner.close();
    }
}
```
### Merge two sorted linked lists

```java
import java.util.Scanner;

class SinglyLinkedListNode {
    public int data;
    public SinglyLinkedListNode next;

    public SinglyLinkedListNode(int nodeData) {
        this.data = nodeData;
        this.next = null;
    }
}

class SinglyLinkedList {
    public SinglyLinkedListNode head;
    public SinglyLinkedListNode tail;

    public SinglyLinkedList() {
        this.head = null;
        this.tail = null;
    }

    public void insertNode(int nodeData) {
        SinglyLinkedListNode node = new SinglyLinkedListNode(nodeData);

        if (this.head == null) {
            this.head = node;
        } else {
            this.tail.next = node;
        }

        this.tail = node;
    }

    // Function to merge two linked lists
    public static SinglyLinkedListNode mergeLists(SinglyLinkedListNode head1, SinglyLinkedListNode head2) {
        SinglyLinkedListNode dummy = new SinglyLinkedListNode(0); // Dummy node to simplify merging
        SinglyLinkedListNode current = dummy;

        while (head1 != null && head2 != null) {
            if (head1.data <= head2.data) {
                current.next = head1;
                head1 = head1.next;
            } else {
                current.next = head2;
                head2 = head2.next;
            }
            current = current.next;
        }

        // If there are remaining nodes in either list
        if (head1 != null) {
            current.next = head1;
        } else {
            current.next = head2;
        }

        return dummy.next; // The merged list is next to the dummy node
    }

    // Function to print the linked list
    public static void printList(SinglyLinkedListNode head) {
        SinglyLinkedListNode current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }
}

public class LinkedListMerge {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Get the number of test cases
        int testCases = scanner.nextInt();

        // Process each test case
        for (int t = 0; t < testCases; t++) {
            SinglyLinkedList list1 = new SinglyLinkedList();
            SinglyLinkedList list2 = new SinglyLinkedList();

            // Read the first linked list
            int n1 = scanner.nextInt();
            for (int i = 0; i < n1; i++) {
                list1.insertNode(scanner.nextInt());
            }

            // Read the second linked list
            int n2 = scanner.nextInt();
            for (int i = 0; i < n2; i++) {
                list2.insertNode(scanner.nextInt());
            }

            // Merge the two linked lists
            SinglyLinkedListNode mergedHead = SinglyLinkedList.mergeLists(list1.head, list2.head);

            // Print the merged linked list
            SinglyLinkedList.printList(mergedHead);
        }

        scanner.close();
    }
}
```
