# Reverse String
--- 
- ## Question:
> Write a function that reverses a string. The input string is given as an array of characters s.
> 
> You must do this by modifying the input array in-place with O(1) extra memory.
---
- ## Example:
> Input: s = ["h","e","l","l","o"]
> 
> Output: ["o","l","l","e","h"]
---
- ## Solution:
**Code :**
```java
class Solution {
    public void reverseString(char[] s) {
        solve(s,0,s.length-1);
    }
    public void solve(char[] s,int start, int end)
    {
        if(start>=end)
            return;
        swap(s,start,end);
        solve(s,++start,--end);
    }
    public void swap(char[]  s,int i,int j)
    {
        char temp=s[i];
        s[i]=s[j];
        s[j]=temp;
    }
}
