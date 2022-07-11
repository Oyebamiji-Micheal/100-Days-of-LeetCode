Code

```Python
class Solution:
    def frequencySort(self, nums: List[int]) -> List[int]:
        res = Counter(nums)
        return sorted(nums, key=lambda num: (res[num], -num))
            
```
