Code
```Python
def checker(nums):
    if len(nums) == 0:
        return 0
    
    N = len(nums)
    max_so_far = nums[0]
    min_so_far = nums[0]
    res = max_so_far

    for i in range(1, N):
        curr_min = nums[i]
        temp_max = max(curr_min, max_so_far * curr_min, min_so_far * curr_min)
        min_so_far = min(curr_min, max_so_far * curr_min, min_so_far * curr_min)
        max_so_far = temp_max

        res = max(max_so_far, res)

    return res
                    

class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        return checker(nums)
```
