### Code

```Python
def checker(nums):
    N = len(nums)
    front = 0
    last = sum(nums)
    res = 0
    for i in range(0, N-1):
        front += nums[i]
        last -= nums[i]
        if front >= last:
            res += 1 
    
    return res
class Solution:
    def waysToSplitArray(self, nums: List[int]) -> int:        
        return checker(nums)
        
```
