Code
```Python
def checker(word1, word2):
    
    N = len(word1)
    M = len(word2)
    matrix = [[0 for i in range(M+1)] for j in range(N+1)]
    
    for i in range(N+1):
        for j in range(M+1):
            if i == 0:
                matrix[i][j] = j
            elif j == 0:
                matrix[i][j] = i
            elif word1[i-1] == word2[j-1]:
                matrix[i][j] = matrix[i-1][j-1]
            else:
                p = min(matrix[i][j-1], matrix[i-1][j], matrix[i-1][j-1])
                matrix[i][j] = 1 + p
    
    return matrix[-1][-1]


class Solution:
    def minDistance(self, word1: str, word2: str) -> int:
        return checker(word1, word2)
```
