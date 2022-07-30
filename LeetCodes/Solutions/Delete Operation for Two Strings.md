Code

```Python
class Solution:
    def minDistance(self, word1: str, word2: str) -> int:
        m = len(word1)
        n = len(word2)
        
        dp = [0] * (m+1) 
        for i in range(n):
            temp = [0] * (m+1)
            for j in range(m):
                if word2[i] == word1[j]:
                    temp[j+1] = dp[j] + 1 
                else:
                    temp[j+1] = max(temp[j], dp[j+1])    
            dp = temp
            
        return m + n - (2 * dp[-1])
        
        
```
