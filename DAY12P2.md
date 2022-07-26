# House Robber
--- 
- ## Question:
> You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and it will automatically contact the police if two adjacent houses were broken into on the same night.
> 
> Given an integer array nums representing the amount of money of each house, return the maximum amount of money you can rob tonight without alerting the police.
---
- ## Example:
> Input: nums = [1,2,3,1]
> 
> Output: 4
---
- ## Solution:
**Code :**
```java
public class Solution {

    public int rob(int[] num) {
        int last = 0;
        int now = 0;
        int tmp;
        for (int n :num) {
            tmp = now;
            now = Math.max(last + n, now);
            last = tmp;
        }
        return now;        
    }
}
