# DSA
public class Main
{ 
    Node head;
    class Node{
        String data;
        Node next;
        
        Node(String data){
            this.data=data;
            this.next=null;
        }
    }
    public void addFirst(String data){
        Node newNode = new Node(data);
        if(head==null){
            head=newNode;
            return;
        }
        newNode.next=head;
        head=newNode;
        
    }
    public void addLast(String data){
        Node newNode = new Node(data);
        if(head==null){
            head=newNode;
            return;
        }
        Node currNode=head;
        while(currNode.next !=null){
            currNode=currNode.next;
        }
        currNode.next=newNode;
    }
    public void printList(){
        
        if(head==null){
            System.out.println("empty");
            return;
        }
        Node currNode=head;
        while(currNode !=null){
            System.out.print(currNode.data+"-->");
            currNode=currNode.next;
        }
        System.out.println("null");
        
    }
	public static void main(String[] args) {
	    Main ll = new Main();
	    ll.addFirst("is");
	    ll.addFirst("a");
	    ll.addFirst("this");
	    ll.addLast("list");
	    ll.printList();
	    
	    

	}
}
# BINARY SEARCH TREE OPRATIONS
public static boolean search(Node root,int key){
    if(root==null){
        return false;
    }
    if(key==root){
        return true;
    }
    else if(root.data>key){
        search(root.left,key);
    }
    else{
        search(root.right,key);
    }
}
	public static void main(String[] args) {
	    int[] values={1,7,3,2,6,5};
	    Node root=null;
	    for(int i =0; i<values.length; i++){
	        root=insert(root,values[i]);
	    }
	    inorder(root);
	    System.out.println();
		
	}
	if(search(root,7)){
	    System.out.println("found");
	    
	    
	}
	else{
	    System.out.println("not found");
	}
}

