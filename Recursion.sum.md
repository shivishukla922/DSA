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
