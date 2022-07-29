# Reverse Words in a String III
--- 
- ## Question:
> Given a string s, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.
---
- ## Example:
> Input: s = "Let's take LeetCode contest"
> 
> Output: "s'teL ekat edoCteeL tsetnoc"
---
- ## Solution:
**Code :**
```java
class Solution {
    public String reverseWords(String s) {
        char[] c=s.toCharArray();
        int i=0,j=0;
        for(;j<c.length;j++)
        {
            if(c[j]==' ')
            {
                reverse(c,i,j-1);
                i=j+1;
            }
           
        } 
        reverse(c,i,j-1);
        return new String(c);
    }
    public void reverse(char[] c,int l, int r)
    {
        while(l<r)
        {
            char temp=c[l];
            c[l++]=c[r];
            c[r--]=temp;
        }
        
    }
}
