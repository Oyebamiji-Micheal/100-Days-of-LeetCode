Approach 1 (Dynamic Programming)  
Code
```Python
class Solution:
    def longestPalindromeSubseq(self, s: str) -> int:
        s1 = s[::-1]
        n = m = len(s)
        dp = [[0]*(m+1) for _ in range(n+1)]
        
        for i in range(n):
            for j in range(m):
                if s[i] == s1[j]:
                    dp[i+1][j+1] = dp[i][j] + 1
                else:
                    dp[i+1][j+1] = max(dp[i+1][j], dp[i][j+1])
        
        return dp[-1][-1]
```

</br>
</br>
</br>

Approach 2 (Memoization)   
Code
```Python
class Solution:
    def longestPalindromeSubseq(self, s: str) -> int:
        memo = {}
        s1 = s[::-1]
        
        def recursion(idx1=0, idx2=0):
            key = (idx1, idx2)
            if key in memo:
                return memo[key]
            elif idx1 == len(s) or idx2 == len(s):
                memo[key] = 0
            elif s[idx1] == s1[idx2]:
                memo[key] = 1 + recursion(idx1+1, idx2+1)
            else:
                option1 = recursion(idx1+1, idx2)
                option2 = recursion(idx1, idx2+1)
                memo[key] = max(option1, option2)
            return memo[key] 
        return recursion(0, 0)
        
```
