Code

```Python
class Solution:
    def largestGoodInteger(self, num: str) -> str:

        res = -1
        string = ""
        for i in num:
            if len(string) == 0:
                string += i
            else:
                if len(string) == 3:
                    x = int(string)
                    if x > res:
                        res = int(string)
                    string = i
                else:
                    if string[0] == i:
                        string += i 
                    else:
                        string = i
        if len(string) == 3:
                    x = int(string)
                    if x > res:
                        res = int(string)
                    string = "" 

        if res == -1:
            return ""
        if res == 0:
            return "000"
        return str(res)
```
