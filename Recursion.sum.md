# DSA
import java.util.*;
public class Main
{
    public  static void printSum(int i,int n,int sum){
        if(n==i){
            sum +=i;
             System.out.println(sum);
            
        return;
        }
       sum +=i;
       printSum(i+1,n,sum);
        
    }
	public static void main(String[] args) {
		
		printSum(1,5,0);
	
	}
}
#BINARY TREE
public class Main
{
    static class Node{
        int data;
        Node left;
        Node right;
        Node(int data){
            this.data= data;
            this.left=null;
            this.right=null;
        }
    }
    static class BinaryTree{
       static int idx=-1;
        public static Node buildTree(int nodes[]){
            idx++;
            if(nodes[idx]==-1){
                return null;
            }
            Node newNode= new Node(nodes[idx]);
            newNode.left=buildTree(nodes);
	    newNode.right=buildTree(nodes);
	    
	    return newNode;
            
            
            
        }
        
    }
	public static void main(String[] args) {
	    int nodes[]={1,2,4,-1,-1,5,-1,-1,3,-1,6,-1,-1};
	    BinaryTree tree= new BinaryTree();
	    
	    Node root=tree.buildTree(nodes);
	    System.out.println(root.data);
	    
	
	}
}
# INORDER ,POSTORDER,PREORDER TRAVERSAL
public class Main
{
    static class Node{
        int data;
        Node left;
        Node right;
        Node(int data){
            this.data= data;
            this.left=null;
            this.right=null;
        }
    }
    static class BinaryTree{
       static int idx=-1;
        public static Node buildTree(int nodes[]){
            idx++;
            if(nodes[idx]==-1){
                return null;
            }
            Node newNode= new Node(nodes[idx]);
            newNode.left=buildTree(nodes);
	    newNode.right=buildTree(nodes);
	    
	    return newNode;
            
            
            
        }
        
    }
    public static void preOrder(Node root){
        if(root==null){
            return;
        }
       
        System.out.print(root.data +" ");
        preOrder(root.left);
        preOrder(root.right);
        
    }
    public static void inOrder(Node root){
        if(root==null){
            return;
        }
        inOrder(root.left);
        System.out.print(root.data +" ");
        inOrder(root.right);
        
    }
    public static void postOrder(Node root){
    if(root==null){
        return;
    }
    
    postOrder(root.left);
    postOrder(root.right);
    System.out.print(root.data +" ");
    }
    
	public static void main(String[] args) {
	    int nodes[]={1,2,4,-1,-1,5,-1,-1,3,-1,6,-1,-1};
	    BinaryTree tree= new BinaryTree();
	    
	    Node root=tree.buildTree(nodes);
	    System.out.println(root.data);
	    preOrder(root);
	   
	    
	    
	
	}
}


#BINARY SEARCH TREE

class BsT{
static class Node{
int data;
Node left;
Node right;
Node(int data)
this.data=data;
}
}
public static Node insert(Node root,int val){
if(root==null){
root new Node(val);
return root;
}
if(root.data>val){
root.left=insert(root.left,val)
}
else{
root.right=insert(root.right,val)
}
return root;
}
 public static void inorder(Node root){
        if(root==null){
            return;
        }
        inorder(root.left);
        System.out.print(root.data+" ");
        inorder(root.right)
	}
	public static void main(String(args[]){
	int values={1 ,3,2};
	Node root=null;
	for(int i =0; i<valuse.length; i++){
	root=insert(root,values[i]);
	}
	inorder(root);
	Sys();
	}
	}
