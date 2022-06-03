Code
```Python
def checker (nums):
    if len(nums) <= 3:
        return nums.index(max(nums))

    else:
        left, right = 0, len(nums)-1
        while right - left >= 3:
            mid = (left + right) // 2
            target = nums[mid]
            if target > nums[mid-1] and target > nums[mid+1]: # target found 
                return mid 
            elif target > nums[mid-1] and target < nums[mid+1]: # target is part of an increasing sequence
                left = mid + 1 
            elif target < nums[mid-1] and target > nums[mid+1]: # target is part of a decreasing sequence
                right = mid - 1
            elif target < nums[mid-1] and target < nums[mid+1]: # target is part of either 
                    left = mid

    return nums.index(max(nums[left:right+1]))

class Solution:
    def findPeakElement(self, nums: List[int]) -> int:
        return checker(nums)
```
