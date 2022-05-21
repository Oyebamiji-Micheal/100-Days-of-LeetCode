### Definition
>-Reverse Polish notation (RPN). [Wikipedia](https://en.wikipedia.org/wiki/Reverse_Polish_notation)

### Explanation
>- First, create an empty list, say ```stack```. Then, loop through the RPN expression.
>- Append integer values only to the stack. Otherwise perform an arithmetic operation on the last two appended integers.
>- Append the result of the arithmetic operation to the stack. 
>- According to the problem constraint, the expression is always valid. Hence, return the last value appended to the stack.

### Algorithm
>- Since operations are performed on one end, the stack data structure is used.

Code
```python
def checker(tokens):
    stack = []
    for i in range(len(tokens)):
        
        if tokens[i] == '+':
            x = stack.pop()
            y = stack.pop() 
            stack.append(int(y) + int(x))
        elif tokens[i] == '-':
            x = stack.pop()
            y = stack.pop() 
            stack.append(int(y) - int(x))
        elif tokens[i] == '*':
            x = stack.pop()
            y = stack.pop() 
            stack.append(int(y) * int(x))
        elif tokens[i] == '/':
            x = stack.pop()
            y = stack.pop() 
            stack.append(int(int(y) / int(x)))
        else:
            stack.append(tokens[i])
    
    return stack[0]

class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        if __name__ == '__main__':
            return checker(tokens)
        
```
