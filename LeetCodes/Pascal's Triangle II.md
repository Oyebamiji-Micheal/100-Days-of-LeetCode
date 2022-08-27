Code

```Python
def checker(row):
    lst = [1]
    for i in range(1, row+1):
        lst.append(1)
        for j in range(len(lst)-2, 0, -1):
            lst[j] = lst[j] + lst[j-1]
    return lst

class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        if __name__ == '__main__':
            return checker(rowIndex)
        
```
