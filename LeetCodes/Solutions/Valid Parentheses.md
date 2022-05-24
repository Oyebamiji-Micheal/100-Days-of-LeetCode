### Explanation
An input string is valid if:  
1. Open brackets must be closed by the same type of brackets.  
2. Open brackets must be closed in the correct order. (LeetCode)

### Algorithm and Data Structure
>- Since all open brackets must be closed by the same type, this means the bracket immediately before a closing bracket must be of the same type as the closing bracket.
>- Thus, keep stacking all open brackets until a closing bracket is to be added, then pop the last value in the stack. If they are not of same type, return false, else continue the process until the end of the list.
>- If after iteration the stack is empty, return true i.e., we find a match for every bracket. Otherwise, return false.

Code
``` Python

def checker(string):

    mapping = {'{' : '}', '[' : ']', '(' : ')'}
    stack = []
    for i in string:
 
        if str(i) == '(' or str(i) == '[' or str(i) == '{':
            stack.append(str(i))
 

        else:
            try:
                x = stack.pop()
            except IndexError:
                return False
            if mapping[x] == str(i):
                continue
            else:
                return False

    if len(stack) == 0:
        return True
    else:
        return False

class Solution:
    def isValid(self, s: str) -> bool:
        if __name__ == '__main__':
            return checker(s)
        
```
