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
