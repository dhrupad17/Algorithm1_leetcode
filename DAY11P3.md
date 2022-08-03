# Letter Case Permutation
--- 
- ## Question:
> Given a string s, you can transform every letter individually to be lowercase or uppercase to create another string.
> 
> Return a list of all possible strings we could create. Return the output in any order.
---
- ## Example:
> Input: s = "a1b2"
> 
> Output: ["a1b2","a1B2","A1b2","A1B2"]
---
- ## Solution:
**Code :**
```java
class Solution {
    List<String> ans =new ArrayList<>();
    public List<String> letterCasePermutation(String s) {
        permute("",s.toLowerCase());
        return ans;
    }
    public void permute(String p, String up)
    {
        if(up.isEmpty())
        {
            ans.add(p);
            return;
        }
        char ch=up.charAt(0);
        if(ch>='0' && ch<='9') {
             permute(p+ch,up.substring(1));
        }else{
            permute(p+Character.toUpperCase(ch),up.substring(1));                                          
            permute(p+ch,up.substring(1));
        }
    }
}
