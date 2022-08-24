Code
```Python
class Solution:
    def triangularSum(self, nums: List[int]) -> int:
        n = len(nums) - 1
        while n != 0:
            for i in range(n):
                nums[i] = (nums[i] + nums[i+1]) % 10
            n -= 1
            
        return nums[0]
            
```
