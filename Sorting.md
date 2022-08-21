# DSA
#QUICKSORT
#time complexity
in avg case O(nlogn)
in wrost case it will be O(n^2) // when smallest or largest ele will be at the last position in the array.

public class Main
{
    public static int partition(int arr[],int l,int h){
        int pivot=arr[h];
        int i =l-1;
        for(int j =l; j<h; j++){
            if(arr[j]<pivot){
                i++;
                int temp =arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
            }
        }
        i++;
        int temp = arr[i];
        arr[i]=arr[h];
        arr[h]=temp;
        return i;
    }
    public static void quickSort(int arr[],int l,int h){
        if(l<h){
        int pivx=partition(arr,l,h);
        quickSort(arr,l,pivx-1);
        quickSort(arr,pivx+1,h);
    }
    }
    
	public static void main(String[] args) {
	    int arr[]={2,4,3,1,5};
	    int n = arr.length;
	    quickSort(arr,0,n-1);
	    for(int i =0; i<n; i++){
	    System.out.print(arr[i] +" ");
	    }
	    System.out.println();
		
	}
}
# MERGE SORT
#TIME COMPLEXITY
nlogn in all cases
public class Main
{
    public static void conquer(int arr[],int s,int mid,int e){
      int  merged[]= new int[e-s+1];
      int idx1=s;
      int idx2=mid+1;
      int x=0;
      while(idx1 <= mid && idx2 <= e){
          if(arr[idx1] <= arr[idx2]){
              merged[x++]=arr[idx1++];
          }
          else{
              merged[x++]=arr[idx2++];
          }
      }
      while(idx1 <=mid){
          merged[x++]=arr[idx1++];
      }
      while(idx2<= e){
          merged[x++]=arr[idx2++];
      }
      for(int i =0, j=s; i<merged.length; i++,j++){
          arr[j]=merged[i];
      }
    }
    public static void divide(int arr[],int s,int e){
        if(s>=e){
            return;
        }
        int mid= s +(e-s)/2;
        divide(arr,s,mid);
        divide(arr,mid+1,e);
        conquer(arr,s,mid,e);
    }
    
	public static void main(String[] args) {
	    int arr[]={2,4,3,1,5};
	    int n = arr.length;
	    divide(arr,0,n-1);
	   
	    for(int i =0; i<n; i++){
	    System.out.print(arr[i] +" ");
	    }
	    System.out.println();
		
	}
}
# BUBBLE SORT
TIME COMPLEXITY
BEST o(N)
WROST o(n^2)
public class Main
{
	public static void main(String[] args) {
	int arr[]={2,1,3,4,5};
	for(int i =0; i<arr.length-1; i++){
	    for(int j = 0; j<arr.length-i-1; j++){
	        if(arr[j]>arr[j+1]){
	            int temp =arr[j];
	            arr[j]=arr[j+1];
	            arr[j+1]=temp;
	        }
	    }
	}
	for(int i =0; i<arr.length; i++){
	System.out.print(arr[i]+" ");
	}
	System.out.println();
	}
}
#SELECTION SORT
#TIME COMPLEXITY
o(N^2)
public class Main
{
	public static void main(String[] args) {
	int arr[]={2,1,3,4,5};
	for(int i =0; i<arr.length-1; i++){
	    int smallest=i;
	    for(int j =i+1; j<arr.length;j++){
	        if(arr[smallest]>arr[j]){
	            smallest=j;
	        }
	    }
	        int temp =arr[smallest];
	        arr[smallest]=arr[i];
	        arr[i]=temp;
	    
	}
	for(int i =0; i<arr.length; i++){
	System.out.print(arr[i]+" ");
	}
	System.out.println();
	}
}
#insertion sort
public class Main
{
	public static void main(String[] args) {
	int arr[]={2,1,3,4,5};
	
	    for(int i=1; i<arr.length;i++){
	       int curr= arr[i];
	       int j =i-1;
	       while(j>=0 && curr <arr[j]){
	           arr[j+1]=arr[j];
	           j--;
	       }
	      arr[j+1]=curr;
	}
	for(int i =0; i<arr.length; i++){
	System.out.print(arr[i]+" ");
	}
	System.out.println();
	}
}
#FIBONACCI
class GFG {
    public static void printFib(int n){
        int f1=0,f2=1,i;
        if(n<1)
            return;
            System.out.print(f1+" ");
        
        for( i =1; i<n; i++){
            System.out.print(f2+" ");
            int next=f1+f2;
            f1=f2;
            f2=next;
        }
    }
	public static void main (String[] args) {
		printFib(9);
	}
}
#Given an integer array nums, return the third distinct maximum number in this array. If the third maximum does not exist, return the maximum number.
class Solution {
    public int thirdMax(int[] nums) {
        if(nums.length==1)
            return nums[0];
        if(nums.length==2){
            return Math.max(nums[0],nums[1]);
        }
        long max1=Long.MIN_VALUE;
        long max2=Long.MIN_VALUE;
        long max3=Long.MIN_VALUE;
        for(int i =0; i<nums.length; i++)
        {
            if(nums[i]==max1 || nums[i]==max2 || nums[i]==max3){
                continue;
            }
            if(nums[i]>max1){
                max3=max2;
                max2=max1;
                max1=nums[i];
           
    }
            else if( nums[i]>max2){
                max3=max2;
                max2=nums[i];
            }
            else if( nums[i]>max3){
                max3=nums[i];
            }
            
}
        if(max3==Long.MIN_VALUE)
            return (int)max1;
        
        
        return (int)max3;
    }
}
#BINARY SEARCH
#QUESTIONS
#SEARCH A KEY IN AN ARRAY
#ITERATIVE
class GFG {
    public static int binarySearch(int arr[],int key){
        int low=0;
        int high=arr.length-1;
        while(low<=high){
            int mid=low +(high-low)/2;
            if(key==arr[mid]){
                return mid;
            }
            else if(key<arr[mid]){
                high=mid-1;
                
            }
            else{
                low=mid+1;
            }
        }
        return -1;
        
    }
	public static void main (String[] args) {
	    GFG ob= new GFG();
	    int arr[]={10,30,50,100,500,701};
	    int n = arr.length;
	    int key=701;
	   int ans= ob.binarySearch(arr,key);
	   if(ans==-1){
	       System.out.println("not found");
	   }
	   else{ 
	       System.out.println("found at " +ans);
	   }
	    
	    
	
	}
}

#RECURSIVE METHOD


class GFG {
    public static int binarySearch(int arr[],int key,int low,int high){
        
        while(low<=high){
            int mid=low +(high-low)/2;
            if(key==arr[mid]){
                return mid;
            }
            else if(key<arr[mid]){
            return binarySearch(arr,key,low,mid-1);
                
            }
            else{
                return binarySearch(arr,key,mid+1,high);
            }
        }
        return -1;
        
    }
	public static void main (String[] args) {
	    GFG ob= new GFG();
	    int arr[]={10,30,50,100,500,701};
	    int n = arr.length;
	    int key=701;
	   int ans= ob.binarySearch(arr,key,0,n-1);
	   if(ans==-1){
	       System.out.println("not found");
	   }
	   else{ 
	       System.out.println("found at " +ans);
	   }
	    
	    
	
	}
}
