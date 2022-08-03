# Combinations
--- 
- ## Question:
> Given two integers n and k, return all possible combinations of k numbers out of the range [1, n].
> 
> You may return the answer in any order.
---
- ## Example:
> Input: n = 4, k = 2
> 
> Output:
[
  [2,4],
  [3,4],
  [2,3],
  [1,2],
  [1,3],
  [1,4],
]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<List<Integer>> combine(int n, int k) {
        List<List<Integer>> ans=new ArrayList<>();
        help(1,n,new ArrayList(),ans,k);
        return ans;
    }
    public void help(int start, int n, List<Integer> curr,List<List<Integer>> ans,int k)
    {
        if(curr.size()==k)
            ans.add(new ArrayList(curr));
        for(int i=start;i<=n;i++)
        {
            curr.add(i);
            help(i+1,n,curr,ans,k);
            curr.remove(curr.size()-1);
        }
    }
}
