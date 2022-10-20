Code

```Python

from math import dist


def get_distance(coordinate):
    return dist(coordinate, [0,0])


def checker(coordinates, target):
    res = {}
    for i in range(len(coordinates)):
        res[i] = get_distance(coordinates[i])
    sort_res = sorted(res.items(), key=lambda x: x[1], reverse=False)
    return [coordinates[sort_res[x][0]] for x in range(target)] 


class Solution:
    def kClosest(self, points: List[List[int]], k: int) -> List[List[int]]:
        return checker(points, k)
```
