## AVL TREE

An AVL tree is a type of self-balancing binary search tree (named after its inventors Adelson-Velsky and Landis). 

``BF=Height of Left Subtree−Height of Right Subtree``

The balance factor can only be ``-1, 0, or 1``. 

### Rotations in AVL tree

-  Left Rotation (LL Case)
-  Right Rotation (RR Case)
-  Left-Right Rotation (LR Case)
-  Right-Left Rotation (RL Case)

### PREORDER

```java
import java.util.Scanner;

class Node{
    int val;
    Node left;
    Node right;
    Node(int val){
        this.val=val;
        this.left=left;
        this.right=right;
    }
}

class AVLTree{
    Node root;
    void preOrder(Node node){
        if(node==null){
            return;
        }
        System.out.println(node.val);
        preOrder(node.left);
        preOrder(node.right);
        
    }
     int height(Node node){
        return (node==null)?0:Math.max(height(node.left),height(node.right));
    }
    int getBalance(Node node){
        return (node==null)?0:height(node.left)-height(node.right);
    }
    Node rightRotate(Node x){
        Node y=x.left;
        Node t2=y.right;
        y.right=x;
        x.left=t2;
        return x;
    }
    Node leftRotate(Node x){
        Node y=x.right;
        Node t2=y.left;
        y.left=x;
        x.right=t2;
        return x;
    }
    Node insert(Node node,int val){
        if(node==null){
            return new Node(val);
        }
        if(val<node.val){
            node.left=insert(node.left,val);
        }
        else if(val>node.val){
            node.right=insert(node.right,val);
        }
        else{
            return node;
        }
        
        
        int balance=getBalance(node);
        
        if(balance>1 && val<node.left.val){
            return rightRotate(node);
        }
        else if(balance<-1 && val>node.right.val){
            return leftRotate(node);
        }
        else if(balance>1 && val>node.left.val){
            node.left=leftRotate(node);
            return rightRotate(node);
        }
        else if(balance<-1 && val<node.right.val){
            node.right=rightRotate(node);
            return leftRotate(node);
        }
        return node;
    }
    void insert(int key){
        root=insert(root,key);
    }
    
}
    



public class Main
{
	public static void main(String[] args) {
	    AVLTree tree=new AVLTree();
	    tree.insert(30);
	    tree.insert(20);
	    tree.insert(40);
	    tree.insert(10);
	    tree.insert(25);
	    tree.insert(35);
	    tree.insert(50);

tree.preOrder(tree.root);
	}
}

```

### INORDER

```java
import java.util.Scanner;

class Node{
    int val;
    Node left;
    Node right;
    Node(int val){
        this.val=val;
        this.left=left;
        this.right=right;
    }
}

class AVLTree{
    Node root;
    void preOrder(Node node){
        if(node==null){
            return;
        }
        preOrder(node.left);
        System.out.println(node.val);
        
        preOrder(node.right);
        
    }
     int height(Node node){
        return (node==null)?0:Math.max(height(node.left),height(node.right));
    }
    int getBalance(Node node){
        return (node==null)?0:height(node.left)-height(node.right);
    }
    Node rightRotate(Node x){
        Node y=x.left;
        Node t2=y.right;
        y.right=x;
        x.left=t2;
        return x;
    }
    Node leftRotate(Node x){
        Node y=x.right;
        Node t2=y.left;
        y.left=x;
        x.right=t2;
        return x;
    }
    Node insert(Node node,int val){
        if(node==null){
            return new Node(val);
        }
        if(val<node.val){
            node.left=insert(node.left,val);
        }
        else if(val>node.val){
            node.right=insert(node.right,val);
        }
        else{
            return node;
        }
        
        
        int balance=getBalance(node);
        
        if(balance>1 && val<node.left.val){
            return rightRotate(node);
        }
        else if(balance<-1 && val>node.right.val){
            return leftRotate(node);
        }
        else if(balance>1 && val>node.left.val){
            node.left=leftRotate(node);
            return rightRotate(node);
        }
        else if(balance<-1 && val<node.right.val){
            node.right=rightRotate(node);
            return leftRotate(node);
        }
        return node;
    }
    void insert(int key){
        root=insert(root,key);
    }
    
}
    



public class Main
{
	public static void main(String[] args) {
	    AVLTree tree=new AVLTree();
	    tree.insert(30);
	    tree.insert(20);
	    tree.insert(40);
	    tree.insert(10);
	    tree.insert(25);
	    tree.insert(35);
	    tree.insert(50);

tree.preOrder(tree.root);
	}
}

```
### POSTORDER


```java
import java.util.Scanner;

class Node{
    int val;
    Node left;
    Node right;
    Node(int val){
        this.val=val;
        this.left=left;
        this.right=right;
    }
}

class AVLTree{
    Node root;
    void preOrder(Node node){
        if(node==null){
            return;
        }
        preOrder(node.left);
        preOrder(node.right);
        System.out.println(node.val);
        
       
        
    }
     int height(Node node){
        return (node==null)?0:Math.max(height(node.left),height(node.right));
    }
    int getBalance(Node node){
        return (node==null)?0:height(node.left)-height(node.right);
    }
    Node rightRotate(Node x){
        Node y=x.left;
        Node t2=y.right;
        y.right=x;
        x.left=t2;
        return x;
    }
    Node leftRotate(Node x){
        Node y=x.right;
        Node t2=y.left;
        y.left=x;
        x.right=t2;
        return x;
    }
    Node insert(Node node,int val){
        if(node==null){
            return new Node(val);
        }
        if(val<node.val){
            node.left=insert(node.left,val);
        }
        else if(val>node.val){
            node.right=insert(node.right,val);
        }
        else{
            return node;
        }
        
        
        int balance=getBalance(node);
        
        if(balance>1 && val<node.left.val){
            return rightRotate(node);
        }
        else if(balance<-1 && val>node.right.val){
            return leftRotate(node);
        }
        else if(balance>1 && val>node.left.val){
            node.left=leftRotate(node);
            return rightRotate(node);
        }
        else if(balance<-1 && val<node.right.val){
            node.right=rightRotate(node);
            return leftRotate(node);
        }
        return node;
    }
    void insert(int key){
        root=insert(root,key);
    }
    
}
    



public class Main
{
	public static void main(String[] args) {
	    AVLTree tree=new AVLTree();
	    tree.insert(30);
	    tree.insert(20);
	    tree.insert(40);
	    tree.insert(10);
	    tree.insert(25);
	    tree.insert(35);
	    tree.insert(50);

tree.preOrder(tree.root);
	}
}

```

