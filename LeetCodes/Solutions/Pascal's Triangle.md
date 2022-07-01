Code

```Python
def checker(numRows):
    
    x = [[1]]

    for i in range(1, numRows):        
        y = x[-1].copy()
        y.append(1)
        
        for j in range(len(y)-2, 0, -1):
            y[j] = y[j] + y[j-1]

        x.append(y) 
    
    return x

class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
          return checker(numRows)
                
                
```
