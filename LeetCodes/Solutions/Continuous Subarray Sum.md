First approach (Accepted)  
Space complexity: O(1)    
Time complexity: O($n^2$)

Code (Algorithm: Prefix Sum)
```Python 
class Solution:
    def checkSubarraySum(self, nums: List[int], k: int) -> bool:
        N = len(nums)
        num = nums[0]
        
        for i in range(1, len(nums)):
            if nums[i] == num == 0:
                return True
            num = nums[i]
            nums[i] = nums[i] + nums[i-1]
            
        for i in range(1, N):
            if nums[i] < k:
                continue
            for j in range(i):
                if j == 0 and nums[i] % k == 0:
                    return True     
                elif j != 0 and (nums[i] - nums[j-1]) % k == 0:
                    return True
        
        return False
                
```     
<br>
<br>
<br>

Second approach (Accepted)  
Space Complex: O(n)  
Time Complexity: O(n)

Code
```Python
class Solution:
    def checkSubarraySum(self, nums: List[int], k: int) -> bool:
        hashmap = {0:-1}
        run_sum = 0
        for idx, val in enumerate(nums):
            run_sum += val
            rem = run_sum % k
            if rem not in hashmap:
                hashmap[rem] = idx
            elif idx - hashmap[rem] > 1:
                return True
            
        return False
        
```
