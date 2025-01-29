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

**Same Tree**

leetcode-100

```java
class Solution {
    public boolean dfs(TreeNode p,TreeNode q){
        if(p==null && q==null){
            return true;
        }
        else if(p==null && q!=null){
            return false;
        }
        else if(p!=null && q==null){
            return false;
        }
        
        if(p.val!=q.val){
            return false;
        }
        return dfs(p.left,q.left) && dfs(p.right,q.right);
        
    }
    public boolean isSameTree(TreeNode p, TreeNode q) {
        if(q==null && p==null){
            return true;
        }
        return dfs(p,q);
        
    }
}
```
**mirror Tree**

```java
class Solution {
    // Function to convert a binary tree into its mirror tree.
    void mirror(Node node) {
        if(node==null){
            return;
        }
        Node temp=node.left;
        node.left=node.right;
        node.right=temp;
        
        mirror(node.left);
        mirror(node.right);
        
    }
}
```
**invert Tree**

leetcode-226

```java
class Solution {

    public TreeNode invertTree(TreeNode root) {
        if(root==null){
            return root;
        }
        TreeNode temp=root.left;
        root.left=root.right;
        root.right=temp;

       invertTree(root.left);
       invertTree(root.right);


      return root;  
        
    }
}
```

**Symmetric Tree**

leetcode-101

```java
class Solution {
    public boolean areMirror(TreeNode p,TreeNode q){
        if(p==null && q==null){
            return true;
        }
        else if(p==null || q==null){
            return false;
        }
        else if(p.val!=q.val){
            return false;
        }
       
       return areMirror(p.left,q.right) && areMirror(p.right,q.left);
    }
    public boolean isSymmetric(TreeNode root) {
        if(root==null){
            return true;
        }
              
        return areMirror(root.left,root.right);
        
        
    }
}
```
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
**Level of a Node in Binary Tree**
**Construct Binary Tree from Parent Array**
**105. Construct Binary Tree from Preorder and Inorder Traversal**
**minimum distance between two given nodes**
**maximum sum leaf to root path**
**odd even level difference**
**ancestors in binary tree**
**remove bst keys outside given range**
**sum tree**


---
---

**Height of Binary Tree**
**Number of leaf nodes**
**Check if given Binary Tree is Height Balanced or Not**
**Write Code to Determine if Two Trees are Identical or Not**
**Given a binary tree, check whether it is a mirror of itself**
**Maximum Path Sum**
**Print Left View of Binary Tree**f
**Print Bottom View of Binary Tree**
**Print a Binary Tree in Vertical Order**
**Diameter of a Binary Tree**
**Level order traversal in spiral form**
**Connect Nodes at Same Level**
**Convert a given Binary Tree to Doubly Linked List**
**Serialize and Deserialize a Binary Tree**
