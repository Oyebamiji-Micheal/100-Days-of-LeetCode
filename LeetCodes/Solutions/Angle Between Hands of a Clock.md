### Explanation

The angle between the hands can be found using the formula below:  
angle = |0.5 x (60 x H - 11 x M)|   
where    
- H is the hour
- M is the minute

Detailed explanation can be found in this [Wikipedia Page](https://en.wikipedia.org/wiki/Clock_angle_problem)   
One thing to note is that if the answer is greater than 180, we return the smaller angle (360 - angle)

Code
```Python
class Solution:
    def angleClock(self, hour: int, minutes: int) -> float:
        
        angle = abs(0.5 * (60 * hour - 11 * minutes))
        if angle > 180:
            return 360 - angle  
        return angle
```
