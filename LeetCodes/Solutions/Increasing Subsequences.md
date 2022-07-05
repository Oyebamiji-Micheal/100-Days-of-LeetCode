Code

```Python
class Solution:
    def findSubsequences(self, nums: List[int]) -> List[List[int]]:
        
        res = set()
        n = len(nums)
        
        def checker(start, cur):
            if len(cur) > 1:
                res.add(tuple(cur))

            if cur:
                last = cur[-1]
            else:
                last = float('-inf')

            for i in range(start, n):
                if nums[i] >= last:
                    cur.append(nums[i])
                    checker(i+1, cur)
                    cur.pop()

        checker(0, [])
        return res
```
