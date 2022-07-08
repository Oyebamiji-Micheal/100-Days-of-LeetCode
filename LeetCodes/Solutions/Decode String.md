Cod

```Python
def check1(char):
    try:
        int(char)
        return True
    except:
        return False 

def check2(char):
    if char.isalpha():
        return True
    else:
        return False

def checker(string):
    stack = []

    for i in string:
        if check1(i):   
            try:
                if check1(stack[-1]):
                    stack.append(stack.pop() + i)
                else:
                    stack.append(i)
            except:
                stack.append(i)       
    
        elif check2(i):
            try:
                if check2(stack[-1]):
                    stack.append(stack.pop() + i)
                else:
                    stack.append(i)
            except:
                stack.append(i)

        elif i == "[":
            stack.append(i) 

        elif i == ']':
            x = stack.pop()
            z = stack.pop()
            y = stack.pop()
            try:
                if check2(stack[-1]):
                    stack.append(stack.pop() + (x * int(y)))  
                else:
                    stack.append(int(y) * x) 
            except:
                stack.append(int(y) * x) 

    return ','.join(stack)

class Solution:
    def decodeString(self, s: str) -> str:
        return checker(s)
        
```
