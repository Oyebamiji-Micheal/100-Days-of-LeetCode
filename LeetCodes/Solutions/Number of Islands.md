Code
```Python
def helper(grid, i, j):
    grid[i][j] = '0'

    x = [(i-1, j), (i+1, j), (i, j-1), (i, j+1)]
    for r, c in x:
        if r >= 0 and c >= 0 and r < len(grid) and c < len(grid[0]) and grid[r][c] == '1':
            helper(grid, r, c)

def checker(grid):
    counter = 0
    for i in range(len(grid)):
        for j in range(len(grid[0])):
            if grid[i][j] == '1':
                counter += 1
                helper(grid, i, j)
    return counter


class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        return checker(grid)
        
```
