Code

Approach 1 (Time efficient, lot of recursion call)
```Python
def helper(stack):
    if len(stack) >= 2:
        val = math.gcd(stack[-1], stack[-2])
        if val > 1:
            x = stack.pop()
            y = stack.pop()
            stack.append(int(x * y / val))
            return helper(stack)             

class Solution:
    def replaceNonCoprimes(self, nums: List[int]) -> List[int]:
        stack = []
        for num in nums:
            if stack:
                stack.append(num)
                helper(stack)
            else:
                stack.append(num)
        return stack

        
```



Approach 2 (Memory efficient, less recursion call)
```Python
def gcd(a, b):
    if (a == b):
        return a

    if (a == 0):
        return b

    if (b == 0):
        return a

    if ((~a & 1) == 1):
        if ((b & 1) == 1):
            return gcd(a >> 1, b)
        else:
            return (gcd(a >> 1, b >> 1) << 1)

    if ((~b & 1) == 1):
        return gcd(a, b >> 1)

    if (a > b):
        return gcd((a - b) >> 1, b)

    return gcd((b - a) >> 1, a)

def helper(stack):
    val = gcd(stack[-1], stack[-2])
    
    if val > 1:
        while len(stack) >= 2:            
            x = stack.pop()
            y = stack.pop()
            if x < y:
                lcm = x / val * y
            else: 
                lcm = y / val * x
            stack.append(int(lcm))
            
            if len(stack) >= 2:
                val = gcd(stack[-1], stack[-2])
                if val <= 1:
                    break                
            
def checker(nums):
    stack = []
    for num in nums:
        if stack:
            stack.append(num)
            helper(stack)
        else:
            stack.append(num)

    return stack

class Solution:
    def replaceNonCoprimes(self, nums: List[int]) -> List[int]:
        return checker(nums)
        
        
```
