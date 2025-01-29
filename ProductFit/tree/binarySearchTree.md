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
**Inorder traversal in BST**

```java
import java.util.Scanner;

class TreeNode{
    int data;
    TreeNode left;
    TreeNode right;
    TreeNode(int val){
        this.data=val;
        this.left=null;
        this.right=null;
    }
}
public class Main
{
    public static void dfs(TreeNode root){
        if(root==null){
            return;
        }
        dfs(root.left);
        System.out.println(root.data);
        dfs(root.right);
    }
	public static void main(String[] args) {
	    Scanner scan=new Scanner(System.in);
	    int totalNodes=scan.nextInt();
	 
	    TreeNode root=null;
	    for(int i=0;i<totalNodes;i++){
	        int data=scan.nextInt();
	        root=insertNode(root,data);
	    }
	    
	    dfs(root);
	}
	public static TreeNode insertNode(TreeNode root,int data){
	    if(root==null){
	        return new TreeNode(data);
	    }
	    if(data<root.data){
	        root.left=insertNode(root.left,data);
	        
	    }
	    else{
	        root.right=insertNode(root.right,data);
	    }
	    return root;
	}
}

```
**Delete node in BST**
leetcode-450

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
    public int min(TreeNode root){
        int min=-1;

        while(root!=null){
            min=root.val;
            root=root.left;
        }
        
        return min;
        
    }
    public TreeNode deleteNode(TreeNode root, int val) {

        if(root==null ){
            return root;
        }
        if(val<root.val){
            root.left=deleteNode(root.left,val);
        }
        else if(val>root.val){
            root.right=deleteNode(root.right,val);
        }
        else{
            
            if(root.left==null) {
                return root.right;
            }
            else if(root.right==null ){
                return root.left;
            }
            else {
                //successor
                root.val=min(root.right);
                root.right=deleteNode(root.right,root.val);
            }
        }
        return root;
        
    }
}
```
**1008. Construct Binary Search Tree from Preorder Traversal**
**pair with given target in bst**

---
---
**Check for BST**
**Lowest Common Ancestor in a BST**
**Ceil in BST**
**K-th Largest Element in BST**
**Largest BST in Binary Tree**
**Merge Two Balanced Binary Search Trees**
**Sorted Array to Balanced BST**

