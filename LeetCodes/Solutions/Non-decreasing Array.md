Given an array nums with n integers, your task is to check if it could become non-decreasing by modifying at most one element.
We define an array is non-decreasing if ```nums[i] <= nums[i + 1]``` holds for every ```i``` (0-based) such that ```(0 <= i <= n - 2)```

### Brute Force
- Create a copy of nums which is sorted, say, ```sorted_nums```
- Iterate over ```nums```.
- If for any ```i```, ```nums[i] >= nums[i + 1]```, modify nums by changing any of the two numbers! 
- If nums needs to be modified again, return false otherwise, keep iterating
- After iteration, check if ```nums``` equals ```sorted_nums```. If yes, return true otherwise, return false.

### Greedy approach
- There are many ways to make ```nums[i]``` and ```nums[i+1]``` non-decreasing, but for simplicity, 
these two are used:
>- Option 1: assign ```nums[i]``` to ```nums[i+1]``` or
>- Option 2: assign ```nums[i+1]``` to ```nums[i]```
- Instead of sorting the array, check if the number just before ```nums[i]``` is greater than the one immediately after. If yes, then option
two is used otherwise, option one is used. 
- This way it's certain ```nums``` will be non-decreasing if at most one element needs to be modified

Code
```Python
class Solution:
    def checkPossibility(self, nums: List[int]) -> bool:
        check = False
        N = len(nums) 
        
        for i in range(N-1):
            if nums[i] > nums[i+1]:
                if check:
                    return False 
                else:
                    if i > 0 and nums[i+1] < nums[i-1]:
                        nums[i+1] = nums[i]
                    else:
                        nums[i] = nums[i+1]   
                    check = True
                    
        if check:
            return True
        
        return True 
                
```
