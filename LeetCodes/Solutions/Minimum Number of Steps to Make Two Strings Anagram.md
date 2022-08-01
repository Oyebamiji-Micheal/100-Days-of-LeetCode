Code

```Python
class Solution:
    def minSteps(self, s: str, t: str) -> int:
        hashmap = {}
        res = 0
        for i in s:
            if i in hashmap:
                hashmap[i] += 1
            else:
                hashmap[i] = 1
        
        for i in t:
            if i in hashmap:
                if hashmap[i] > 0:
                    hashmap[i] -= 1
                else:
                    res += 1
            else:
                res += 1
                
        return res
        
```
