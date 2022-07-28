Approach 1 (Dynamic Programming)   
Code
```Python
class Solution:
    def longestCommonSubsequence(self, text1: str, text2: str) -> int:
        m = len(text1)
        n = len(text2)
        
        dp = [0] * (m+1) 
        for i in range(n):
            temp = [0] * (m+1)
            for j in range(m):
                if text2[i] == text1[j]:
                    temp[j+1] = dp[j] + 1 
                else:
                    temp[j+1] = max(temp[j], dp[j+1])    
            dp = temp
            
        return dp[-1]
```

</br>
</br>

Approach 2 (Memoization)  
Code

```Python
class Solution:
    def longestCommonSubsequence(self, text1: str, text2: str) -> int:
        memo = {}
        
        def lsc(idx1=0, idx2=0):
            key = (idx1, idx2)
            if key in memo:
                return memo[key]
            elif idx1 == len(text1) or idx2 == len(text2):
                memo[key] = 0
            elif text1[idx1] == text2[idx2]:
                memo[key] = 1 + lsc(idx1+1, idx2+1)
            else: 
                option1 = lsc(idx1+1, idx2)
                option2 = lsc(idx1, idx2+1)
                memo[key] = max(option1, option2)
            return memo[key]
        return lsc(0, 0)
                
```
