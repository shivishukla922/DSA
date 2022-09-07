# DSA
public  static int printfact(int n){
        if(n==1||n==0){
           
            
        return 1;
        }
      int fact=printSum(n-1);
      int fact_n=n*fact;
      return fact_n;
        
    }
	public static void main(String[] args) {
	    int n=5;
		
	int ans=	printfact(n);
	System.out.println(ans);
	
}
#PRINT FIBBONACHI SERIES USING RECURSION
public class Main
{
    public static void printFib(int a,int b,int n){
        if(n==0){
            return;
        }
        int c=a+b;
        System.out.print(c);
        printFib(b,c,n-1);
    }
    
	public static void main(String[] args) {
	    int a=0,b=1;
	    System.out.print(a);
	    System.out.print(b);
	    int n=7;
	    printFib(a, b, n-2);
	
	}
}
