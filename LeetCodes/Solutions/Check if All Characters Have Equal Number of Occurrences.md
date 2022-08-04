Code

```Python
class Solution:
    def areOccurrencesEqual(self, s: str) -> bool:
        hashmap = {}
        for i in s:
            if i in hashmap:
                hashmap[i] += 1
            else:
                hashmap[i] = 1
        
        val = hashmap[s[0]]
        
        for i in hashmap.values():
            if i != val:
                return False
        
        return True
        
```
