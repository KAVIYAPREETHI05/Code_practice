### 107. Binary Tree Level Order Traversal II

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
    public List<List<Integer>> levelOrderBottom(TreeNode root) {

        List<List<Integer>>result=new LinkedList<>();
        if(root==null){
            return result;
        }
        Queue<TreeNode>q=new LinkedList<>();

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
        Collections.reverse(result);  // result.addFirst(temp);  (addFirst() eliminates the need of reversing)
        return result;
        
    }
}
```

### 199. Binary Tree Right Side View
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
### 236. lowest common ancestor 
```java
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {

        if(root==null) return null;

        if(root==p || root==q) return root;

        TreeNode left=lowestCommonAncestor(root.left,p,q);
        TreeNode right=lowestCommonAncestor(root.right,p,q);

        if(left!=null && right!=null) return root;

        return left==null? right:left;
        
    }
}
```
### 112.PathSum
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
### 114.Flatten binary tree of linked list



