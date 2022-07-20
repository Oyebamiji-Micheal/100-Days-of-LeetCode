Space Complexity: O(n)  
Time Complexity: O(n)

Code
```Python
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        res = 0
        hashmap = {}
        run_sum = 0
        
        for num in nums:
            run_sum += num
            if run_sum == k:
                res += 1
            diff = run_sum - k
            if diff in hashmap:
                res += hashmap[diff]
            hashmap[run_sum] = 1 + hashmap.get(run_sum, 0)

        return res
        
 ```
