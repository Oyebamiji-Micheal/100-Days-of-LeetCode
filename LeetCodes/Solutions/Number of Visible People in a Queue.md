### Explanation (fairly optimized)
- If there exist ```i``` and ```j``` such that ```j``` > ```i``` and ```heights[j]``` > ```heights[i]```, then ```heights[j+1]```, ```heights[j+2]```, ... will all be invisible to ```i```
- In addition to the above logic, by using stack to keep track of heights and corresponding indices, all visible heights can be obtained using the explanation below
>- For every ```heights[i]``` check if it is greater than the last value in stack
>- If yes, keep popping from the stack until there a value greater than ```heights[i]```. All values popped will be invisible to heights[i]
>- Otherwise these values will be visible 


Code
```Python
class Solution:
    def canSeePersonsCount(self, heights: List[int]) -> List[int]:
        N = len(heights)
        res = [0] * N
        stack = []
            
        for i in range(N):
            if stack:
                for j in range(-1, -1-len(stack), -1):
                    idx = stack[-1][-1]
                    res[idx] += 1
                    
                    if heights[i] > stack[-1][0]:
                        stack.pop()
                        
                    else:
                        break
                        
                stack.append([heights[i], i])
                
            else:
                stack.append([heights[i], i])
            
        return res
```
