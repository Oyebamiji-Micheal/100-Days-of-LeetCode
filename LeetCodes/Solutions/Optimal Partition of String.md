Code (Greedy Approach)

```Python
class Solution:
    def partitionString(self, s: str) -> int:
        res = set()        
        ans = 0
        
        for char in s:
            if char not in res:
                res.add(char)
            else:
                ans += 1
                res = set(char)
                
        return ans + 1

```
