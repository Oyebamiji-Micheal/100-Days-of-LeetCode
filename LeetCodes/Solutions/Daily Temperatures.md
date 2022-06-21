Code

```Python
def checker(temperatures):
    res = [0] * len(temperatures)
    stack = []

    for index, temperature in enumerate(temperatures):
        while len(stack) != 0 and temperature > stack[-1][0]:
            temp_val, temp_idx = stack.pop()
            diff = index - temp_idx
            res[temp_idx] = diff

        stack.append([temperature, index])
    return res 

class Solution:
    def dailyTemperatures(self, temperatures: List[int]) -> List[int]:
        return checker(temperatures)
```
