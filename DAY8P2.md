# Populating Next Right Pointers in Each Node
--- 
- ## Question:
> You are given a perfect binary tree where all leaves are on the same level, and every parent has two children. The binary tree has the following definition:
> 
> Populate each next pointer to point to its next right node. If there is no next right node, the next pointer should be set to NULL.
> 
> Initially, all next pointers are set to NULL.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2019/02/14/116_sample.png)
> Input: root = [1,2,3,4,5,6,7]
> 
> Output: [1,#,2,3,#,4,5,6,7,#]
---
- ## Solution:
**Code :**
```java
class Solution {
    public Node connect(Node root) {
        if(root==null)return null;
        Node head=root;
        Queue<Node> q=new LinkedList<>();
        q.add(head);
        while(!q.isEmpty()){
            int n=q.size();
            ArrayList<Node> arr=new ArrayList<>();
            while(n-->0){
                Node temp=q.poll();
                if(temp.left!=null){
                    q.add(temp.left);
                }
                if(temp.right!=null){
                    q.add(temp.right);
                }
                arr.add(temp);
            }
            for(int i=0;i<arr.size()-1;i++){
                arr.get(i).next=arr.get(i+1);
            }
        }
        return root;
    }
}
