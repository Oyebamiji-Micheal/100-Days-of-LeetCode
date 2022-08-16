Code
```Python
class Solution:
    def countPoints(self, rings: str) -> int:
        hashmap = {}
        n = len(rings)
        
        for idx in range(1, n, 2):
            color = rings[idx-1]
            rod = rings[idx]
            
            if rod in hashmap:
                if color not in hashmap[rod]:
                    hashmap[rod].add(color)
            else:
                hashmap[rod] = {color}
        
        res = 0
        for val in hashmap.values():
            if len(val) == 3:
                res += 1
        
        return res
```
