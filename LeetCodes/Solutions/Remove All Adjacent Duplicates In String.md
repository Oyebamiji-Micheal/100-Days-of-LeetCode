Code
```Python
class Solution:
    def removeDuplicates(self, s: str) -> str:
        stack = []
        N = len(s)
        
        for i in range(N):
            char = s[i]
            if stack:
                if char == stack[-1]:
                    stack.pop()
                else:
                    stack.append(char)
                    
            else:
                stack.append(char)
        
        return ''.join(stack)        
```
