Code

```Python
class Solution:
    def findLongestChain(self, pairs: List[List[int]]) -> int:
        pairs.sort()
        N = len(pairs)
        dp = [1] * N
        
        for i in range(1, N):
            for j in range(i):
                if pairs[i][0] > pairs[j][1] and dp[i] < dp[j] + 1:
                    dp[i] = dp[j] + 1
                    
        return max(dp)
        
        

```
