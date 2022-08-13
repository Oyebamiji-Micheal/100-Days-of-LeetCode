Code
```Python
class Solution:
    def findOriginalArray(self, changed: List[int]) -> List[int]:
        hashmap = {}
        
        for num in changed:
            if num in hashmap:
                hashmap[num] += 1
            else:
                hashmap[num] = 1
                
        res = []  
        changed.sort()
        
        for num in changed:
            if hashmap[num] != 0 and hashmap.get(num*2, 0) == 0:
                return []
            
            elif num == 0: 
                if hashmap[num] >= 2:
                    res.append(num)
                    hashmap[num] -= 2
                elif hashmap[num] != 0:
                    return []
                
            elif hashmap[num] != 0 and hashmap[num*2] != 0:
                res.append(num)
                hashmap[num] -= 1
                hashmap[num*2] -= 1
        
        return res
```
