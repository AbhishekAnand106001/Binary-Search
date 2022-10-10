// peak element using recursive binary search

import java.util.*;
import java.lang.*;
import java.io.*;
import java.util.Scanner;

class Main
{
    static int findPeakUtil(int arr[], int low, int high, int n)
    {
        int mid = low + (high - low) / 2;
        
        if((mid == 0 || arr[mid-1]<=arr[mid] && 
        (mid == n-1) || arr[mid+1]<=arr[mid]))
        
        return mid;
        
        else if(mid > 0 && arr[mid-1] > arr[mid])
        return findPeakUtil(arr, low, (mid-1), n);
        
        else 
        return findPeakUtil(arr, (mid+1), high, n);
    }
    
    static int findPeak(int arr[], int n)
    {
        return findPeakUtil(arr, 0, n-1, n);
    }
    
    public static void main(String[] args)
    {
        System.out.println("Enter the size of array");
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int arr[] = new int[n];
        System.out.println("Enter the elements of array");
        for(int i=0; i<n; i++)
        {
            arr[i] = sc.nextInt();
        }
        System.out.println(findPeak(arr, n));
 

        // int arr[] = {1,3,20,4,1,0};
        // int n=arr.length;
        // System.out.println(findPeak(arr, n));
    }
    }