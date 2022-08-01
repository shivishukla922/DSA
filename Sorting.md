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
