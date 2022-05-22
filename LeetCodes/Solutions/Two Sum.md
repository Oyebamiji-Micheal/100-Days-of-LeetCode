
### Explanation
>- Given an integer array ```nums```, find two indices such that ```nums[i] + nums[j] = target and i ≠ j```
>- An approach will be to check all possible indices and return the one which satisfies the question
>- This can be done using a nested for loop. i.e., for all ```nums[i]```, check if ```target - nums[i]``` is in the list

### Algorithm
>- A nested loop runs at a time complexity of O(n²) 
>- However, checking our values in a dictionary instead of a list reduces the time complexity to O(n) 


Code
```python

def checker(data, target):
    d = {}
    for idx,val in enumerate(data):
        d[val] = idx
        
    for j in range(len(data)):
        query = target - data[j]
        if query in d and d[query] != j:
            return [j, d[query]]

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        return checker(nums, target)
    
```
