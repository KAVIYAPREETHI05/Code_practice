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

### 589.PREORDER

```java
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/

class Solution {
    public  void preorderTraversal(Node root,List<Integer>result){
        if(root==null){
            return;
        }

        result.add(root.val);
        for(int i=0;i<root.children.size();i++){
            preorderTraversal(root.children.get(i),result);
        }
        
       
    }
    public List<Integer> preorder(Node root) {
        List<Integer>result=new LinkedList<>();
        preorderTraversal(root,result);

        return result;
        
    }
}
```

### 590.POSTORDER

```java
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
}
*/

class Solution {
    public void postorderTraversal(Node root,List<Integer>result){
        if(root==null){
            return;
        }
        for(int i=0;i<root.children.size();i++){
            postorderTraversal(root.children.get(i),result);
        }
        result.add(root.val);
    }
    public List<Integer> postorder(Node root) {
        List<Integer>result=new LinkedList<>();

        postorderTraversal(root,result);
        return result;
        
    }
}
```

### INORDER

```java
class Solution {
    public void inorderTraversal(Node root,List<Integer>result){
        if(root==null){
            return;
        }
        int length=root.children.size();
        for(int i=0;i<length-1;i++){
            inorderTraversal(root.children.get(i),result);
        }
        result.add(root.val);
        if(length>0)
        inorderTraversal(root.children.get(length-1),result);
    }
    public List<Integer> inorder(Node root) {
        List<Integer>result=new LinkedList<>();

        inorderTraversal(root,result);
        return result;
        
    }
}
```

### 4.29 LEVEL ORDER TRAVERSAL

```java
class Solution {
    public List<List<Integer>> levelOrder(Node root) {
        List<List<Integer>>result=new LinkedList<>();
        if(root==null){
            return result;
        }
        Queue<Node>q=new LinkedList<>();
        q.add(root);
        

        while(!q.isEmpty()){
            int size=q.size();
            List<Integer>temp=new LinkedList<>();
            for(int i=0;i<size;i++){
                Node node=q.poll();
                temp.add(node.val);
                for(Node eachNode:node.children){
                    q.offer(eachNode);
                }
            }
            result.add(temp);
        }
        return result;
        
    }
}
```

### ZIGZAG TRAVERSAL

```java
class Solution {
    public List<List<Integer>> levelOrder(Node root) {
        List<List<Integer>>result=new LinkedList<>();
        if(root==null){
            return result;
        }
        Queue<Node>q=new LinkedList<>();
        q.add(root);
        

        while(!q.isEmpty()){
            int size=q.size();
            List<Integer>temp=new LinkedList<>();
            for(int i=0;i<size;i++){
                Node node=q.poll();
                temp.add(node.val);
                for(Node eachNode:node.children){
                    q.offer(eachNode);
                }
            }
            result.add(temp);
        }
        for(int i=0;i<result.size();i++){
            if(i%2!=0){
                Collections.reverse(result.get(i));  //use deque
            }
        }
        return result;
        
    }
}
```

### sum of all nodes
### max depth 

