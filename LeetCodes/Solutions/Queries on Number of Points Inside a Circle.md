### Explanation

The euclidean distance between two points $[x_1, y_1] and [x_2, y_2]$ is given by the formula   
distance = $√((y_2 - y_1)^2 + (x_2 - x_1)^2)$

Code
```Python
class Solution:
    def countPoints(self, points: List[List[int]], queries: List[List[int]]) -> List[int]:
        res = []
        for query in queries:
            count = 0
            for point in points:
                if math.dist(point, query[:2]) <= query[-1]:
                    count += 1
            res.append(count)
            
        return res
```
 
