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
