Code

```Python
def checker(nums):

    if len(nums) == 1:
        return nums[0]

    lo = 0
    hi = len(nums) - 1

    while hi - lo > 2:
        mid = (lo + hi) // 2

        if nums[mid] > nums[mid-1] and nums[mid] < nums[mid+1]:
            return nums[mid]

        elif nums[mid] == nums[mid+1]:
            if mid % 2 == 0:
                lo = mid + 2
            else:
                hi = mid - 1

        else:
            if mid % 2 == 0:
                hi = mid - 2
            else:
                lo = mid + 1
    
    if hi - lo <= 1:
        mid = (lo+hi) // 2
        return nums[mid]
    
    if nums[lo] == nums[lo+1]:
        return nums[lo+2]
    
    else:
        return nums[lo]

class Solution:
    def singleNonDuplicate(self, nums: List[int]) -> int:
        return checker(nums)
        
```
