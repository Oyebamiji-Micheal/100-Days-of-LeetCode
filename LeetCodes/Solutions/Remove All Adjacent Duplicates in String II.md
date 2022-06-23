Code

```Python
def helper(i, s, stack, k):
    while stack and s[i] == stack[-1][0]:
        string, val = stack.pop()
        if val + 1 != k:
            stack.append([s[i], val+1])
            break

class Solution:
    def removeDuplicates(self, s: str, k: int) -> str:
        N = len(s)
        stack = [[s[0], 1]]
        
        for i in range(1, N):
            if len(stack) == 0:
                stack.append([s[i], 1])
                
            elif s[i] == stack[-1][0]:
                helper(i, s, stack, k)
                       
            else:
                stack.append([s[i], 1])
                
        string = ''
        for i in stack:
            string += i[0] * i[1]
            
        return string
```
