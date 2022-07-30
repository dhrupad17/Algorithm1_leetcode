# Max Area of Island
--- 
- ## Question:
> You are given an m x n binary matrix grid. An island is a group of 1's (representing land) connected 4-directionally (horizontal or vertical.) You may assume all four edges of the grid are surrounded by water.
> 
> The area of an island is the number of cells with a value 1 in the island.
> 
> Return the maximum area of an island in grid. If there is no island, return 0.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/05/01/maxarea1-grid.jpg)
> Input: grid = [[0,0,1,0,0,0,0,1,0,0,0,0,0]
> 
> [0,0,0,0,0,0,0,1,1,1,0,0,0]
> 
> [0,1,1,0,1,0,0,0,0,0,0,0,0]
> 
> [0,1,0,0,1,1,0,0,1,0,1,0,0]
> 
> [0,1,0,0,1,1,0,0,1,1,1,0,0]
> 
> [0,0,0,0,0,0,0,0,0,0,1,0,0]
> 
> [0,0,0,0,0,0,0,1,1,1,0,0,0]
> 
> [0,0,0,0,0,0,0,1,1,0,0,0,0]]
> 
> Output: 6
> 
> Explanation: The answer is not 11, because the island must be connected 4-directionally.
---
- ## Solution:
**Code :**
```java
class Solution {
    public int maxAreaOfIsland(int[][] grid) {
        int max=0;
        for(int i=0;i<grid.length;i++)
        {
            for(int j=0;j<grid[0].length;j++)
            {
                max=Math.max(max,dfs(grid,i,j));
            }
        }
        return max;
    }
    public int dfs(int[][] grid, int r, int c)
    {
        if(r<0||r>=grid.length||c<0|| c>=grid[0].length||grid[r][c]==0)
        {
            return 0;
        }
        grid[r][c]=0;
        return 1+dfs(grid,r+1,c)+dfs(grid,r-1,c)+dfs(grid,r,c-1)+dfs(grid,r,c+1);
    }
}
