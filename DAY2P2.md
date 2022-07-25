# Rotate Array
--- 
- ## Question:
> Given an array, rotate the array to the right by k steps, where k is non-negative.
---
- ## Example:
> Input: nums = [1,2,3,4,5,6,7], k = 3
> 
> Output: [5,6,7,1,2,3,4]
---
- ## Solution:
**Code :**
```java
class Solution {
    public static void reverse(int[] arr,int i,int j)
 {
   int low=i;
   int high=j;
   while(low<high)
   {
     int temp=arr[low];
     arr[low]=arr[high];
     arr[high]=temp;
     low++;
     high--;
   }
 }
  public static void rotate(int[] arr,int k)
   {
     k=k%arr.length;
     if(k<0)
        k=k+arr.length;
     //part1
     reverse(arr,0,arr.length-k-1);
     //part2
     reverse(arr,arr.length-k,arr.length-1);
     //part3
     reverse(arr,0,arr.length-1);
   }

}
