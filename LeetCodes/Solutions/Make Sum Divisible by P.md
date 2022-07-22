Code

```Python
class Solution:
    def minSubarray(self, nums: List[int], p: int) -> int:
        rem_nums = sum(nums) % p
        if rem_nums == 0:
            return 0
        
        hashmap = {0: -1}
        run_sum = 0
        n = res = len(nums)
        
        for idx, val in enumerate(nums):
            run_sum +=  val
            temp_rem = run_sum % p
            rem = temp_rem - rem_nums
            
            if rem < 0:
                rem += p
                
            if rem in hashmap:
                res = min(res, idx-hashmap[rem])
            hashmap[temp_rem] = idx
         
        if res < n:
            return res
        return -1
        
        
```
