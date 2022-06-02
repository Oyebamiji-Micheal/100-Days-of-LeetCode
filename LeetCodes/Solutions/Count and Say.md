Code
```Python
def checker(n):
    string = '1'

    for i in range(n-1):
        x = ''
        temp = ''

        for j in string:
            if temp:
                if j == temp[-1]:
                    temp += j

                else:
                    res = str(len(temp)) + temp[0]
                    x += res
                    temp = ''
                    temp += j

            else:
                temp += j
                
        if temp:
            res = str(len(temp)) + temp[0] 
            x += res
        string = x

    return string


class Solution:
    def countAndSay(self, n: int) -> str:
        return checker(n)
        
```
