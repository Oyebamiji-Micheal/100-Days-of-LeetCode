Code

```Python
class Solution:
    def subarraysDivByK(self, nums: List[int], k: int) -> int:
        hashmap = {}
        run_sum = 0
        res = 0
        for num in nums:
            run_sum += num
            rem = run_sum % k
            if rem in hashmap:
                res += 1 + hashmap[rem]
                hashmap[rem] += 1
            elif rem == 0:
                hashmap[rem] = 1
                res += 1
            else:
                hashmap[rem] = 0
                
        return res
```
