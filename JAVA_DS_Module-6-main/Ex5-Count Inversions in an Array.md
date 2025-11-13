# Ex5 Count Inversions in an Array

## DATE:
10.11.2025

## AIM:
To write a Java program to count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

## Algorithm
1. Start the program.  
2. Read the number of elements and store them in an array.  
3. Use a modified merge sort to count inversions:  
   - Recursively split the array into halves and count inversions in each half.  
   - While merging two sorted halves, count cross inversions when an element from the right half is placed before elements remaining in the left half.  
4. Sum inversions from left half, right half, and cross inversions.  
5. Display the total inversion count.  
6. Stop the program.

## Program:
```java
/*
Program to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j
Developed by: Kishore B
RegisterNumber: 212224100032
*/
import java.util.Scanner;

public class CountInversions {
    static long mergeCount(int[] arr, int[] temp, int left, int mid, int right) {
        int i = left, j = mid + 1, k = left;
        long invCount = 0;
        while (i <= mid && j <= right) {
            if (arr[i] <= arr[j]) {
                temp[k++] = arr[i++];
            } else {
                temp[k++] = arr[j++];
                invCount += (mid - i + 1);
            }
        }
        while (i <= mid) temp[k++] = arr[i++];
        while (j <= right) temp[k++] = arr[j++];
        for (i = left; i <= right; i++) arr[i] = temp[i];
        return invCount;
    }

    static long mergeSortCount(int[] arr, int[] temp, int left, int right) {
        long invCount = 0;
        if (left < right) {
            int mid = left + (right - left) / 2;
            invCount += mergeSortCount(arr, temp, left, mid);
            invCount += mergeSortCount(arr, temp, mid + 1, right);
            invCount += mergeCount(arr, temp, left, mid, right);
        }
        return invCount;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();
        int[] arr = new int[n];
        System.out.println("Enter the elements:");
        for (int i = 0; i < n; i++) arr[i] = sc.nextInt();
        int[] temp = new int[n];
        long inversions = mergeSortCount(arr, temp, 0, n - 1);
        System.out.println("Number of inversions: " + inversions);
        sc.close();
    }
}
```
## OUTPUT 
<img width="953" height="157" alt="image" src="https://github.com/user-attachments/assets/6fc7558e-20ad-48c4-b2cc-eb51c4ff35a4" />

## RESULT
Thus the Java program to count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j is implemented successfully.
