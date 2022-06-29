### Explanation Greedy Apprach
- Sort both strings to consider the optimal permutaion
- Check if a string can break then order and vice versa

Code
```Python
class Solution:
    def checkIfCanBreak(self, s1: str, s2: str) -> bool:

        def checker(s1, s2, N):
            for i in range(N):
                if s2[i] < s1[i]:
                    return False
            return True
    
        s1 = sorted(s1)
        s2 = sorted(s2)
        N = len(s1)
        
        for i in range(N):
            if s1[i] < s2[i]:
                res = checker(s1, s2, N)
                return res
                
        return True
                
```
