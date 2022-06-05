### Explanation
- Because strings are immutable in python, convert ```senate```(string) to list
- Loop through ```senate``` with the aim of counting eligible senators from both parties 
- For every senator, check if there's a ban on the senator's party. If 'true', the senator does not count in the current voting and the next if any, otherwise count the senator
- Repeat the process until all senators left (who can vote) are from the same party

Code
```Python
def checker(senate):
    
    senate = list(senate)
    ban_D = 0
    ban_R = 0
    
    while True:
        D = 0
        R = 0
 
        for idx, i in enumerate(senate):
            if i == 'D':
                if ban_D:
                    senate[idx] = 'l'
                    ban_D -= 1
                else:
                    D += 1
                    ban_R += 1
           
            elif i == 'R':
                if ban_R:
                    senate[idx] = 'l'
                    ban_R -= 1
                else:
                    R += 1
                    ban_D += 1
                    
        
        if (D > 0 and ban_D > 0) or (R > 0 and ban_R) or (D == R):
            continue
        else:
            break

        
    if D > R:
        return 'Dire'
    else:
        return 'Radiant' 

class Solution:
    def predictPartyVictory(self, senate: str) -> str:
        return checker(senate)
```
