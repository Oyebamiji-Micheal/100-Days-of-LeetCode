In a Unix-style file system, a period '.' refers to the current directory, a double period '..' refers to the directory up a level, and any multiple consecutive slashes (i.e. '//') are treated as a single slash '/'. For this problem, any other format of periods such as '...' are treated as file/directory names. (Leetcode)

### Explanation
- Split ```path``` and iterate through it once
- create an empty list, say ```stack```
- for every element ```i``` in path, apply the above rule
- Stack data structure is used because operations are performed from a single end (last in first out)

Code
```Python
class Solution:
    def simplifyPath(self, path: str) -> str:
        path = path.split('/')
        stack = ['/']
    
    
        for i in path:
            if i == '..':
                if len(stack) >= 3:
                    stack.pop()
                    stack.pop()
            
            elif i != '.' and i != '':
                stack.append(i)
                stack.append('/')
                
        if len(stack) == 1:
            return ''.join(stack)
        return ''.join(stack[:-1])
```
