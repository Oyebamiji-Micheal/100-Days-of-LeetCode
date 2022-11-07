Code

```Python
class Solution:
    def maxFrequency(self, nums: List[int], k: int) -> int:
        nums.sort()
        left = right = 0
        run_total = res = 0
        N = len(nums)
        
        while right < N:
            run_total += nums[right]
            while (nums[right] * (right-left+1)) > run_total + k:
                run_total -= nums[left]
                left += 1
            
            res = max(res, right-left+1)
            right += 1
            
        return res
```
