### Brute Force
- Use python inbuilt function ```min()``` to get the minimum element in ```nums```

### Algorithm
- Python's ```min()``` function runs in O(n). But, the problem states "You must write an algorithm that runs in O(log n) time." 
- Since ```nums``` is a 'rotated sorted list', we can use binary search to reduce the time complexity.

Code
```Python
def checker(nums):
    if len(nums) <= 3:
        return min(nums)

    lo = 0
    hi = len(nums) - 1
     
    while lo - hi < 2:       
        mid = (lo + hi) // 2
        if nums[mid] < nums[mid - 1]:
            return nums[mid]
        elif nums[mid] > nums[-1]:
            lo = mid + 1
        else:
            hi = mid - 1

    return min(nums[lo:hi+1])

class Solution:
    def findMin(self, nums: List[int]) -> int:
        return checker(nums)
```
