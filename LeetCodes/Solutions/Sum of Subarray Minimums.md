Code
```Python

def checker(arr): 
    stack = []
    sum = 0
    run_sum = 0
    
    for num in arr:
        run_count = 1
        while stack:
            if stack[-1][0] < num:
                break
            value, count = stack.pop()
            run_count += count
            run_sum -= value * count

        stack.append((num, run_count))
        run_sum += num * run_count
        sum += run_sum
        
    return sum % (pow(10, 9) + 7)

class Solution:
    def sumSubarrayMins(self, arr: List[int]) -> int:
        return checker(arr)
    

 ```
                
