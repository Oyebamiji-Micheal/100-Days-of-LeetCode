Code

```Python
class Solution:
    def arrayChange(self, nums: List[int], operations: List[List[int]]) -> List[int]:
        res = {}
        for idx, val in enumerate(nums):
            res[val] = idx
        for i in operations:
            res[i[1]] = res.pop(i[0])
        for key, val in res.items():
            nums[val] = key
            
        return nums
        
```
