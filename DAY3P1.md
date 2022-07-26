# Move Zeroes
--- 
- ## Question:
> Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.
> 
> Note that you must do this in-place without making a copy of the array.
---
- ## Example:
> Input: nums = [0,1,0,3,12]
> 
> Output: [1,3,12,0,0]
---
- ## Solution:
**Code :**
```java
class Solution {
    public void moveZeroes(int[] nums) {
        if(nums==null||nums.length==0)
            return;
        int c=0;
        for(int i:nums)
        {
            if(i!=0)
            {
                nums[c++]=i;
            }
        }
        while(c<nums.length)
        {
            nums[c++]=0;
        }
        
    }
}
