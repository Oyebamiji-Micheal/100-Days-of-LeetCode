```Python
import math


def checker(n):
    primes = [True for i in range(n)]
    primes[:2] = [False, False]
    for i in range(2, int(math.sqrt(n))+1):
        if primes[i]:
            primes[pow(i, 2) : n : i] = [False for i in range(len(primes[pow(i, 2) : n : i]))]

    return sum(primes)


class Solution:
    def countPrimes(self, n: int) -> int:
        return checker(n)
```
