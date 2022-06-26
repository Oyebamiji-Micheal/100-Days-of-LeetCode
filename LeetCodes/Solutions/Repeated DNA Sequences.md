Code
```Python
class Solution:
    def findRepeatedDnaSequences(self, s: str) -> List[str]:
        res = {}
        N = len(s)
        for i in range(10, N+1):
            if s[i-10:i] in res:
                res[s[i-10:i]] += 1
            else:
                res[s[i-10:i]] = 1
        
        return [k for k,v in res.items() if v > 1]
```
