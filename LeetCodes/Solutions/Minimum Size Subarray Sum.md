Code
```Python
def checker(nums, target):
    left_pointer, total, res = 0, 0, float('inf')
    
    for i in range(len(nums)):
        total += nums[i]
        
        while total >= target:
            res = min(i - left_pointer + 1, res)
            total -= nums[left_pointer]
            left_pointer += 1
            
    if res == float('inf'): 
        return 0
    else: 
        return res
            

class Solution:
    def minSubArrayLen(self, target: int, nums: List[int]) -> int:
        return checker(nums, target)
 ```
