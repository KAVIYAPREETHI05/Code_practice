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

## BINARY TREE

A binary tree is a hierarchical data structure where each node has at most two child nodes, referred to as the left child and the right child. 

### Types of binary trees

* **Full Binary Tree**: Every node has either 0 or 2 children.
* **Complete Binary Tree**: All levels, except possibly the last, are completely filled, and the last level has all nodes as far left as possible.
* **Perfect Binary Tree**: All internal nodes have 2 children, and all leaf nodes are at the same level.
* **Skewed Binary Tree**: A tree where all nodes only have one child (left-skewed or right-skewed).
* **Balanced Binary Tree**: The height of the left and right subtrees of every node differ by at most 1.


**PathSum**
leetcode-112
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
    public boolean hasSum(TreeNode root,int target,int curr){
        if(root==null){
            return false;
        }
        int currSum=root.val+curr;
        if(currSum==target && root.left==null && root.right==null){
            return true;
        }
        return hasSum(root.left,target,currSum) || hasSum(root.right,target,currSum);
    }
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root==null){
            return false;
        }
        int sum=0;
        return hasSum(root,targetSum,sum);

        
    }
}
```
**Average of levels of binary tree**

leetcode-637

```java
class Solution {
    public List<Double> averageOfLevels(TreeNode root) {
        List<Double> result=new LinkedList<>();
        if(root==null){
            return result;
        }
        Queue<TreeNode> q=new LinkedList<>();

        q.offer(root);
        while(!q.isEmpty()){
            int size=q.size();
            double avg=0;

            for(int i=0;i<size;i++){
                TreeNode node=q.poll();
                avg+=node.val;

                if(node.left!=null){
                    q.offer(node.left);
                }
                if(node.right!=null){
                    q.offer(node.right);
                }

            }
            double levelAvg=avg/size;
            result.add(levelAvg);
        }
        return result;
        
    }
}
```



**Level of a Node in Binary Tree**
**Same Tree**
**mirror Tree**
**invert Tree**

**Symmetric Tree**
**leaf nodes**
**nn-leaf nodes**

---level order---


**left view**
```java
/* A Binary Tree node
class Node
{
    int data;
    Node left, right;

    Node(int item)
    {
        data = item;
        left = right = null;
    }
}*/
class Solution {
    ArrayList<Integer> leftView(Node root) {
        ArrayList<Integer>result=new ArrayList<>();
        if(root==null){
            return result;
        }
        Queue<Node>q=new LinkedList<>();
        
        q.add(root);
        
        while(!q.isEmpty()){
            int size=q.size();
            int temp=-1;
            for(int i=0;i<size;i++){
                Node node=q.poll();
                if(temp==-1){
                    result.add(node.data);
                    temp=0;
                }
                if(node.left!=null){
                    q.offer(node.left);
                }
                if(node.right!=null){
                    q.offer(node.right);
                }
            }
        }
        return result;
    }
}
```
**right view**
leetcode-199

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
    public List<Integer> rightSideView(TreeNode root) {
        List<Integer>result=new LinkedList<>();
        if(root==null) return result;
        Queue<TreeNode> q=new LinkedList<>();
        q.offer(root);
        while(!q.isEmpty()){
            int size=q.size();
                TreeNode node=new TreeNode();
            for(int i=0;i<size;i++){
                node=q.poll();

                if(node.left!=null){
                    q.offer(node.left);
                }
                if(node.right!=null){
                    q.offer(node.right);
                }
            }
            result.add(node.val);

        }
        return result;
        
    }
}
```
**Zigzag view**
leetcode-103
```java
class Solution {
    public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
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

                if(node.left!=null){
                    q.offer(node.left);
                }
                if(node.right!=null){
                    q.offer(node.right);
                }
            }
            result.add(temp);
        }
        for(int i=0;i<result.size();i++){
            if(i%2!=0){
                Collections.reverse(result.get(i));
            }
        }


return result;

/* instead of collections.reverse using addFirst
 for(int i=0;i<result.size();i++){
            if(i%2!=0){
                LinkedList<Integer> reversedList=new LinkedList<>();

                for(Integer num: result.get(i)){
                    reversedList.addFirst(num);
                }
                result.set(i,reversedList);
            }
        }
*/


        
    }
}
```
**Boundary view**

Binary Tree	| Binary Search Tree (BST)
----------------|-------------------------
No specific ordering of nodes.	|Nodes follow specific ordering rules.
Search Time 𝑂(𝑛)| O(logn) for balanced BST.
No specific order|Produces nodes in sorted order.
General-purpose hierarchical data.	|Efficient searching and sorting.

## BINARY SEARCH TREE


In binary search tree, the value of every node in the left subtree is less than the value of the parent node.

The value of every node in the right subtree is greater than the value of the parent node.

Some implementations of BST do not allow duplicate values.

If we perform inorder traversal in binary tree, the element will be in ascending order.

**Insert node in BST**
leetcode-701

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
    public TreeNode insertIntoBST(TreeNode root, int val) {
        if(root==null){
            return new TreeNode(val);
        }
        if(val<root.val){
                root.left=insertIntoBST(root.left,val);
            
           
        }
        else{
                root.right=insertIntoBST(root.right,val);
           
        }
        return root;
        
    }
}
```

**Search in BST**
leetcode-700

```java
class Solution {
    public TreeNode searchBST(TreeNode root, int val) {
        if(root==null || root.val==val){
            return root;
        }
        if(val<root.val){
            return searchBST(root.left,val);

        }
        else{
            return searchBST(root.right,val);
        }
        
        
    }
}
```



