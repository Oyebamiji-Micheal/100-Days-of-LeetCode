Code

```Python
class Solution:
    def countConsistentStrings(self, allowed: str, words: List[str]) -> int:
        hashmap = set(allowed)
        res = 0
        
        for word in words:
            for char in word:
                if char not in hashmap:
                    res -= 1
                    break
            res += 1
            
        return res
        
```
