Code

```Python
class Solution:
    def groupThePeople(self, groupSizes: List[int]) -> List[List[int]]:
        hashmap = {}
        res = []
        
        for idx, val in enumerate(groupSizes):
            if val in hashmap:
                hashmap[val].append(idx)
            else:
                hashmap[val] = [idx]
            if len(hashmap[val]) == val:
                res.append(hashmap[val])
                hashmap[val] = []
                
        return res 
```
