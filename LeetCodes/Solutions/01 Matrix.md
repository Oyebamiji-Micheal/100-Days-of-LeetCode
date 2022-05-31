

```Python

def checker(matrix):
     
    queue = []    
    for i in range(len(matrix)):
        for j in range(len(matrix[i])):
            if matrix[i][j] == 0:
                queue.append((i, j))    
    
            else:
                matrix[i][j] = '1'
    
    for row, column in queue:
        for x, y in [(row+1, column), (row-1, column), (row, column-1), (row, column+1)]:
            if x >= 0 and y >= 0 and x < len(matrix) and y < len(matrix[0]) and matrix[x][y] == '1':
                matrix[x][y] = matrix[row][column] + 1
                queue.append((x, y))

    return matrix

class Solution:
    def updateMatrix(self, mat: List[List[int]]) -> List[List[int]]:
        return checker(mat)
        
```
