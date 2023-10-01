---
title: QuickSort
date: 2023-10-01
tags:
  - algorithm
  - quicksort
  - sort
---

The idea of QuickSort is by allowing the elements to sort themselves by finding their respective correct positions
The algorithm can be divided into 2 steps
- Sorting + Returning the Pivot
- Recursively executing this with the new High and Low values

![](notes/1.General/Algorithms/attachments/QuickSort%202023-10-01%2019.43.42.excalidraw.svg)
%%[🖋 Edit in Excalidraw](notes/1.General/Algorithms/attachments/QuickSort%202023-10-01%2019.43.42.excalidraw.md), and the [dark exported image](notes/1.General/Algorithms/attachments/QuickSort%202023-10-01%2019.43.42.excalidraw.dark.svg)%%

```cpp
#include <vector>

void swap(vector <int>& arr, int s1, int s2){
    int t = arr[s1];
    arr[s1] = arr[s2];
    arr[s2] = t;
}

int partition(vector <int>& arr, int L, int H){
    int piv = L;
    int i = L;
    int j = H;
    while (i<j){
	    while ( arr[i] <= arr[piv] && i<H-1){ i++; };
	    cout << "The Left thing: " << arr[i] << endl;
	    while (arr[j] > arr[piv] && j > L){j--;}
	    cout << "The Right thing: " << arr[j] << endl;
	    if (i<j){
	        swap(arr, i, j);
	        cout << "Swapping " << i << " " << j << endl;
	    };
    };
    swap(arr, piv, j);
    
    return j;
}

void quickSort(vector <int>& arr, int L, int H){
    if (L < H){
       int piv = partition(arr, L, H);
        quickSort(arr, L, piv-1);
        quickSort(arr, piv+1, H);
    }
}

int main(){
	vector <int> a {4, 6, 2, 5, 7, 9, 1, 3};
	
    quickSort(a, 0, a.size()-1);
	for (int i =0 ; i < a.size(); i++){
		cout << " " << a[i];
	}
	
	return 0;

}
```

