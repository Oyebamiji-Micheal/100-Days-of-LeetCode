Code

```Python
class Solution:
    def reverseParentheses(self, s: str) -> str:
        stack = [] 
        for char in s:
            if char == ')':
                if stack[-1] == '(':
                    stack.pop()
                else:
                    temp = stack.pop()
                    temp = temp[::-1]
                    stack.pop()
                    if stack and stack[-1] != '(':
                        stack[-1] += temp
                    else:
                        stack.append(temp)
            elif char != '(':
                if stack and stack[-1] != '(':
                    stack[-1] += char
                else:
                    stack.append(char)
            else:
                stack.append(char)
                
        return stack[0]
```
