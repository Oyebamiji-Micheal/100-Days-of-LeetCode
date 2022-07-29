Code
```Python
class Solution:
    def countSubstrings(self, s: str) -> int:
        res = 0
        n = len(s)
        dp = [[0]*n for i in range(n)]

        for i in range(n):
            res += 1
            dp[i][i] = 1

        for i in range(n-1):
            if s[i] == s[i+1]:
                res += 1
                dp[i][i+1] = 1

        for i in range(2, n):
            for j in range(i, n):
                if s[j-i] == s[j] and dp[j-i+1][j-1] == 1:
                    dp[j-i][j] = 1
                    res += 1
        return res

        
```
