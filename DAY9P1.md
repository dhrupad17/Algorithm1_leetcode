# 01 Matrix
--- 
- ## Question:
> Given an m x n binary matrix mat, return the distance of the nearest 0 for each cell.
> 
> The distance between two adjacent cells is 1.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/04/24/01-1-grid.jpg)
> Input: mat = [[0,0,0],[0,1,0],[0,0,0]]
> 
> Output: [[0,0,0],[0,1,0],[0,0,0]]
---
- ## Solution:
**Code :**
```java
class Solution {
    public int[][] updateMatrix(int[][] mat) {
        Queue<int[]> q=new LinkedList();
        for(int i=0;i<mat.length;i++)
        {
            for(int j=0;j<mat[0].length;j++)
            {
                if(mat[i][j]==0)
                {
                    q.offer(new int[] {i,j});
                }
                else
                {
                    mat[i][j]=-1;
                }
            }
        }
        int dir[][]={{-1,0},{1,0},{0,-1},{0,1}};
        while(!q.isEmpty())
        {
            int[] x=q.poll();
            for(int[] d:dir)
            {
                int r=x[0]+d[0];
                int c=x[1]+d[1];
                if(r<0||c<0||r>=mat.length||c>=mat[0].length||mat[r][c]!=-1)
                {
                    continue;
                }
                q.add(new int[] {r,c});
                mat[r][c]=mat[x[0]][x[1]]+1;
            }
        }
        return mat;
}
}
