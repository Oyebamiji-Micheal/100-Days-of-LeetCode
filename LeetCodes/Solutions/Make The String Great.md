Code
```Python
class Solution:
    def makeGood(self, s: str) -> str:
        stack = []
        
        for char in s:
            if stack:
                condition_1 = stack[-1].islower() and char.isupper() and stack[-1] == char.lower()
                condition_2 = stack[-1].isupper() and char.islower() and stack[-1].lower() == char
                if condition_1 or condition_2:
                    stack.pop()
                else:
                    stack.append(char)
            else:
                stack.append(char)
        
        return ''.join(stack)
        
```
