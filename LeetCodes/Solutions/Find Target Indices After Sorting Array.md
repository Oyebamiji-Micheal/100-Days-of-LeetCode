Code
```Python

class Solution:
    def targetIndices(self, nums: List[int], target: int) -> List[int]:
        nums.sort()
        res = []
        
        for idx, num in enumerate (nums):
            if num == target:
                res.append(idx)
                
        return res
        
```
