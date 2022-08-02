# Merge Two Binary Trees
--- 
- ## Question:
> You are given two binary trees root1 and root2.
> 
> Imagine that when you put one of them to cover the other, some nodes of the two trees are overlapped while the others are not. You need to merge the two trees into a new binary tree. The merge rule is that if two nodes overlap, then sum node values up as the new value of the merged node. Otherwise, the NOT null node will be used as the node of the new tree.
> 
> Return the merged tree.
> 
> Note: The merging process must start from the root nodes of both trees.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/02/05/merge.jpg)
> Input: root1 = [1,3,2,5], root2 = [2,1,3,null,4,null,7]
> 
> Output: [3,4,5,5,4,null,7]
---
- ## Solution:
**Code :**
```java
class Solution {
    public TreeNode mergeTrees(TreeNode r1, TreeNode r2) {
        if(r1 == null && r2 == null) 
           return null;
        else if (r1 == null) 
            return r2;
        else if (r2 == null) 
            return r1;  
        return new TreeNode(r1.val+r2.val,mergeTrees(r1.left,r2.left),mergeTrees(r1.right,r2.right));
        
    }
}
