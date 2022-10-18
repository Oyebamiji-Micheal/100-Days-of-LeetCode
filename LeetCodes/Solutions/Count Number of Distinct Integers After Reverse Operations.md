Code

```Python

class Solution:
    def countDistinctIntegers(self, nums: List[int]) -> int:
        res = set()
        for num in nums:
            if num not in res:
                res.add(num)
            rev = int(str(num)[::-1])
            if rev not in res:
                res.add(rev)
        return len(res)
```
