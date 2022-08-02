Code

```Python
class Solution:
    def findingUsersActiveMinutes(self, logs: List[List[int]], k: int) -> List[int]:
        ans = [0] * (k)
        hashmap = {}
        for log in logs:
            if log[0] in hashmap:
                hashmap[log[0]].add(log[1])
            else:
                hashmap[log[0]] = {log[1]}
                
        for val in hashmap.values():
            l = len(val)
            ans[l-1] += 1
            
        return ans
```
