### Dynamic Programming
- Create a ```n(rows)``` by ```m(columns)``` matrix
- Populate the whole matrix with 0
- Initialize all elements in the topmost row by 1 and the all elements in the first column by 1
- Iterate the entire array
- By adding the element directly above and to the left of our current position, we can compute the number of paths so far
- After iteration, return the bottom right most element 

```Python
def checker(cols, rows):
    matrix = [[0 for _ in range(cols)] for _ in range(rows)]

    for i in range(rows):
        matrix[i][0] = 1
    
    for j in range(cols):
        matrix[0][j] = 1

    for row in range(1, rows):
        for col in range(1, cols):
            matrix[row][col] = matrix[row-1][col] + matrix[row][col-1]
    
    return matrix[-1][-1]

class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        if __name__ == "__main__":
            return checker(m, n)
         
         
```
