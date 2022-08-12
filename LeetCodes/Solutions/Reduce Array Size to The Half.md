Code

```Python
class Solution:
    def minSetSize(self, arr: List[int]) -> int:
        hashmap = {}
        
        for num in arr:
            if num in hashmap:
                hashmap[num] += 1
            else:
                hashmap[num] = 1
        
        res = 0
        temp = len(arr)
        length = temp / 2
        
        for num in sorted(hashmap.values(), reverse=True):
            if temp <= length:
                return res
            else:
                temp -= num
                res += 1
                
        return res
            
```
