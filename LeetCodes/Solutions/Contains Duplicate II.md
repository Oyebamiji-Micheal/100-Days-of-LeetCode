Code

```Python
def checker(nums, query):
    res = {}
    for i in range(len(nums)):
        if nums[i] not in res:
            res[nums[i]] = i
        else:
            if nums[res[nums[i]]] == nums[i] and abs(res[nums[i]] - i) <= query:
                return True
            else:
                res[nums[i]] = i
    
    return False

class Solution:
    def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
        return checker(nums, k)
```
