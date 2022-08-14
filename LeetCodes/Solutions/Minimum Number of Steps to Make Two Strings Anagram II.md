Code
```Python
class Solution:
    def minSteps(self, s: str, t: str) -> int:
        hashmap_s = Counter(s)
        hashmap_t = Counter(t)
        res = 0
        
        def helper(hashmap1, hashmap2):
            temp = 0
            for key, val in hashmap1.items():
                if key in hashmap2:
                    temp += abs(hashmap1[key] - hashmap2[key])
                    hashmap1[key] = hashmap2[key] = 0
                else:
                    temp += hashmap1[key]
            return temp
        
        res = helper(hashmap_s, hashmap_t) + helper(hashmap_t, hashmap_s)
        return res   
```
