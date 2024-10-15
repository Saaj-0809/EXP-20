## EXPERIMENT 20

## AIM:

To study and implement Sorting Algorithm
1. Selection sort
2. Insertion sort
3. Bubble sort

## THEORY:

In C++, sorting refers to the process of arranging elements in a specific order, typically in ascending or descending order. Sorting algorithms can be applied to arrays, vectors, or other containers to reorder the elements based on their values.<br>

1. *Selection Sort:*
* Selection Sort works by repeatedly finding the minimum element from the unsorted part of the array and swapping it with the first unsorted element.
* Time Complexity: O(n²) for all cases.
* Space Complexity: O(1) (in-place sorting). <br>
 
![Selection_sort](https://github.com/sarakanyal03/CDS_Experiment20/blob/main/Selection_sort.png)

2. *Insertion Sort:*
* Insertion Sort works by building a sorted array one element at a time. It picks each element and inserts it into its correct position within the already sorted part of the array.
* Time Complexity: O(n²) in the worst case; O(n) in the best case (already sorted).
* Space Complexity: O(1) (in-place sorting). <br>
 
![Insertion_sort](https://github.com/sarakanyal03/CDS_Experiment20/blob/main/Insertion_sort.png)

3. *Bubble Sort:*
* Bubble Sort repeatedly swaps adjacent elements if they are in the wrong order. The largest element "bubbles up" to its correct position after each pass.
* Time Complexity: O(n²) in the worst case.
* Space Complexity: O(1) (in-place sorting). <br>
  
 ![Bubble_sort](https://github.com/sarakanyal03/CDS_Experiment20/blob/main/Bubble_sort.png)


## 1.Selection sort:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;
void swap(int *a,int *b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
void s_sort(int *a, int elements){
    int n=0;
    int *b;
    while (n!=elements){
        b=a+1;
        for (int i=0; i< (elements-1)-n;i++){
            if(*a>*b){
                swap(a,b);
            }
             b++;
        }
        n++;
        a++;
    }   
}
int main(){
    int no_el;
    cout <<"How many elements in your array ?"<<endl;
    cin>>no_el;
    int arr[no_el];
    cout<<"Enter "<<no_el<<" Elements:"<<endl;
    for (int i=0;i<no_el;i++){
        cin>>arr[i];
    }
    cout<<"Sorted Array:";
    s_sort(&arr[0],no_el);
    for (int i=0; i<no_el;i++){
        cout<<arr[i]<<" ";
    }
    return 0;
}

~~~

## OUTPUT:

<img width="432" alt="image" src="https://github.com/user-attachments/assets/b0c61ff9-5c6a-46b6-b128-ff36aaa865aa">

## 2.Insertion sort:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;
void insertionSort(int arr[], int n ){
    for (int i = 1; i < n; i++){
        int key=arr[i];
        int j=i-1;
        while (j>=0 && arr[j]>key){
            arr[j+1]=arr[j];
            j--;
        }
        arr[j+1]=key;
    }
}
int main(){
    int arr[]={64, 25, 12, 22, 11};
    int n= sizeof(arr)/ sizeof(arr[0]);
    cout<< "Original array: ";
    for (int i=0;i<n;i++){
        cout << arr[i] << " ";
    }
    insertionSort (arr,n);
    cout<< "\n Sorted array: ";
    for (int i = 0; i < n; i++){
        cout <<arr[i] << " ";
    }
    return 0;
}
~~~

## OUTPUT:

<img width="446" alt="image" src="https://github.com/user-attachments/assets/8abaf9b3-5155-4f0f-bc06-88772f71b316">

## 3.Bubble sort:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;
void swap(int *a,int *b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
int main(){
    int elements;
    cout<<"How many elements in the array?:";
    cin>>elements ;
    int array[elements];
    cout<<" Enter elements: ";
    for (int i = 0; i < elements ; i++){
        cin>>array[i];
    }
    for (int i = 0; i < elements; i++){
        cout<<array[i]<<" ";
    }
    int n=0;
    while(n!=elements){
        for(int i = 0 ; i < elements - n ; i++){
            if (array[i] > array[i+1]){
                swap(&array[i], &array[i+1]);
            }
        }
        n++;
    }
    cout << "\nSorted array is: "<< endl;
    for(int i = 0; i < elements; i++){
        cout << array[i]<<" ";
    }
    return 0;
}
~~~

## OUTPUT:

<img width="427" alt="image" src="https://github.com/user-attachments/assets/cd24b0ee-f12b-4cc0-a908-0ed44769af24">

## CONCLUSION:
These algorithms are primarily useful for educational purposes, and while they work well on small datasets, more advanced sorting algorithms such as Quick Sort, Merge Sort, or Heap Sort are generally preferred for large datasets due to their better performance.
