## Tree

The most optimized searching algorithm is **tree**.

### Terminologies

* **Node**: The smallest individual element in a tree.
* **Root**: The topmost node in a tree.
* **Parent**: A node with child nodes.
* **Child**: A node derived from another node (parent).
* **Leaf**: A node with no children.
* **Edge**: The connection between two nodes.
* **Depth**: The level of a node in the tree (distance from the root).
* **Height**: The longest path from the root to a leaf.
* **Subtree**: A tree consisting of a node and its descendants.
* **Cousins**: Nodes from different parent but in same level.
* **Siblings**: Nodes from same parent and same level.

### operations

* insertion
* deletion
* traversal
* search
* height calculation
* merge

### Applications

* Hierarchical data representation
* searching and sorting
* Expression Parsing
* Database indexing
* Networking

### Types of trees

  * Binary tree (Full Binary,Complete Binary tree, Prefect Binary tree,Balanced binary tree, Binary search tree, Strict Binary tree)
  * AVL tree
  * Red Black tree
  * B tree
  * B+ tree
  * Heap tree
  * Trie(prefix tree)
  * suffix tree

### treeNode implementation

```java
import java.util.Scanner;
class TreeNode{
    int data;
    TreeNode left;
    TreeNode right;
    
    TreeNode(int data){
        this.data=data;
        this.left=null;
        this.right=null;
    }
}
public class Main
{
    public static void preOrder(TreeNode root){
        if(root==null){
            return;
        }
        System.out.print(root.data);
        preOrder(root.left);
        preOrder(root.right);
    }
	public static void main(String[] args) {
	    Scanner scan=new Scanner(System.in);
	    int totalNodes=scan.nextInt();
	    
	    TreeNode root=new TreeNode(scan.nextInt());
	    
	    for(int i=1;i<totalNodes;i++){
	        int data=scan.nextInt();
	        insertNode(root,data);
	    }
	    
	    preOrder(root);
	    
	    
	    
	}
	
	public static void insertNode(TreeNode root,int data){
	    TreeNode current=root;
	    TreeNode newNode=new TreeNode(data);
	    
	    while(true){
	        if(data<current.data){
	           if(current.left==null){
	               current.left=newNode;
	               break;
	           }
	           else{
	               current=current.left;
	           }
	        }
	        else{
	            if(current.right==null){
	                current.right=newNode;
	                break;
	            }
	            else{
	                current=current.right;
	            }
	            
	        }
	    }
	}
}
```


DFS |BFS
----|-----
Explores as far as possible along each branch before backtracking. |	Explores all neighbors of a node level by level.
Uses a stack (or recursion) for traversal.|	Uses a queue for traversal.
Preorder (visits a node before its children), PostOrder, InOrder|	Level-order (visits nodes level by level).
Solving mazes or puzzles,Topological sorting.	| Finding shortest paths in unweighted graphs, Web crawlers.


### DFS
---
**PREORDER**

leetcode-144

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public void dfs(TreeNode root,List<Integer>result){
         if(root==null){
            return;
        }
        result.add(root.val);
        dfs(root.left,result);
        dfs(root.right,result);
    }
    public List<Integer> preorderTraversal(TreeNode root) {
        
        List<Integer> result=new ArrayList<>();

        dfs(root,result);

       

        return result;
        
    }
}
```
**INORDER**

leetcode-94
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public void dfs(TreeNode root,List<Integer>result){
        if(root==null){
            return;
        }
        dfs(root.left,result);
        result.add(root.val);
        dfs(root.right,result);
    }
    public List<Integer> inorderTraversal(TreeNode root) {
        ArrayList<Integer>result=new ArrayList<>();
        dfs(root,result);
        return result;
        
    }
}
```

**POSTORDER**

leetcode-145

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {

    public void dfs(TreeNode root,List<Integer>result){
        if(root==null){
            return;
        }
        dfs(root.left,result);
        dfs(root.right,result);
        result.add(root.val);
    }
    public List<Integer> postorderTraversal(TreeNode root) {

        List<Integer> result=new ArrayList<>();

        dfs(root,result);
        return result;
        
    }
}

```

### BFS
---
**LEVEL ORDER**

leetcode-102

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        
        List<List<Integer>>result=new LinkedList<>();
        if(root==null){
            return result;
        }
        Queue<TreeNode> q=new LinkedList<>();

        q.offer(root);

        while(!q.isEmpty()){
            int size=q.size();
            List<Integer>temp=new LinkedList<>();

            for(int i=0;i<size;i++){
            TreeNode node=q.poll();
            temp.add(node.val);

            if(node.left!=null)
              q.offer(node.left);
            if
            (node.right!=null)
              q.offer(node.right);
            }

            result.add(temp);
              
        }
        return result;        
    }
}
```


Binary Tree	| Binary Search Tree (BST)
----------------|-------------------------
No specific ordering of nodes.	|Nodes follow specific ordering rules.
Search Time 𝑂(𝑛)| O(logn) for balanced BST.
No specific order|Produces nodes in sorted order.
General-purpose hierarchical data.	|Efficient searching and sorting.






