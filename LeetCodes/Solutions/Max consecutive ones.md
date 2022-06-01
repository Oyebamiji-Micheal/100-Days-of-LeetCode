### Explanation
- Create two variables ```l``` and ```max_l``` representing the 'current length' and 'length calculated so far'
- Iterate ```nums``` once
- After iteration, return the maximum between ```l``` and ```max_l```

Code
```Python

def checker(nums):
    l = 0
    max_l = 0
    for i in range(len(nums)):
        if nums[i] == 1:
            l += 1
            
        else:
            max_l = max(max_l, l)
            l = 0
    
    return max(max_l, l)

class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        return checker(nums)
        
        ```
