# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE: 03-10-2026
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.
## Algorithm
1. Read n and store the n input elements into an array nums.
2. Build a max heap by calling heapify on all non-leaf nodes from n/2 − 1 down to 0.
3. Repeatedly swap the first element (maximum) with the last unsorted element and reduce the heap size by one.
4. After each swap, call heapify on the root to restore the max-heap property.
5. Continue until all elements are extracted, producing a fully sorted array, then print the result.

## Program:
```JAVA
/*
Program tosorts a given array of integers in ascending order without using built-in sorting functions
Developed by : Vasanth N
RegisterNumber: 212224110060
*/\
import java.util.*;

public class Solution {
    
    private void swap(int[] arr, int index1, int index2) {
        int temp = arr[index1];
        arr[index1] = arr[index2];
        arr[index2] = temp;
    }

    // Heapify the subtree rooted at index i
    private void heapify(int[] arr, int n, int i) {
        //Type code here....
        int largest = i;         // Initialize largest as root
        int left = 2 * i + 1;    // Left child index
        int right = 2 * i + 2;   // Right child index

        // If left child is larger than root
        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }

        // If right child is larger than current largest
        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }

        // If largest is not root
        if (largest != i) {
            swap(arr, i, largest);

            // Recursively heapify the affected subtree
            heapify(arr, n, largest);
        }
    }

    private void heapSort(int[] arr) {
        //Type code here....
        int n = arr.length;

        // Step 1: Build a max heap
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(arr, n, i);
        }

        // Step 2: Extract elements from heap one by one
        for (int i = n - 1; i > 0; i--) {
            // Move current root (max) to end
            swap(arr, 0, i);

            // Call heapify on reduced heap
            heapify(arr, i, 0);
        }
    }

    public int[] sortArray(int[] nums) {
        heapSort(nums);
        return nums;
    }

    // ------------------ MAIN METHOD ------------------
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution solution = new Solution();

        //System.out.println("Enter number of elements:");
        int n = sc.nextInt();
        
        int[] nums = new int[n];
        //System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        int[] sorted = solution.sortArray(nums);
        System.out.println("Sorted array:");
        System.out.println(Arrays.toString(sorted));

        sc.close();
    }
}

```

## Output:
<img width="1268" height="360" alt="image" src="https://github.com/user-attachments/assets/38d61c42-86c6-44a3-9550-8f26195f7065" />



## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
