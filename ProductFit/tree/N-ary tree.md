## N-ary Tree

An N-ary tree is a tree data structure where each node can have at most N children.

This is a generalization of the binary tree, where each node can have at most two children (left and right).

```java
class Node {
    int val;
    List<Node> children;  // Stores multiple children

    Node(int val) {
        this.val = val;
        this.children = new ArrayList<>();
    }
}

```

