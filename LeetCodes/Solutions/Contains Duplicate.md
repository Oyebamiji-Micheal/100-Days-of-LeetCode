Code

```Python
def checker(nums):
    res = {}
    for i in range(len(nums)):
        if nums[i] not in res:
            res[nums[i]] = i
        else:
            return True
        
    return False

class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        return checker(nums)
   
```
