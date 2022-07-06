Code
```Python
class Solution:
    def parseBoolExpr(self, expression: str) -> bool:
        
        def helper_and(count_f, count_t, stack):
            if count_f:
                stack.append('f')
            else:
                stack.append('t')
        
        def helper_or(count_f, count_t, stack):
            if count_t:
                stack.append('t')
            else:
                stack.append('f')
        
        def helper_not(count_f, count_t, stack):
            if count_t:
                stack.append('f')
            else:
                stack.append('t')
        
        def helper(stack): 
            count_t = 0
            count_f = 0
            
            while True:
                if stack[-1] == 't':
                    count_t += 1
                elif stack[-1] == 'f':
                    count_f += 1
                else:
                    break
                stack.pop()
                
            opp = stack.pop()
            if opp == '&':
                helper_and(count_f, count_t, stack)
            elif opp == '|':
                helper_or(count_f, count_t, stack)
            else:
                helper_not(count_f, count_t, stack)
            
        stack = []
        
        for char in expression:
            if char == ')' or char == '}':
                helper(stack)
            elif char != ',' and char != '(' and char != '{':
                stack.append(char)
        
        if stack[-1] == 't':
            return True
        else:
            return False
```
