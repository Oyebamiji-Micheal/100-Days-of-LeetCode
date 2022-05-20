### Explanation
>- The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1 (source: LeetCode)
>- Since we are always repeating the same thing, i.e. taking the sum of the two preceding ones, we can use recursion
>- Almost all recursive solutions have a base case. In this case, our recursion call ends when n is 0 or 1 

### Algorithm
>- To optimize our code, we will use the concept of memoization. For example F(6) = F(5) + F(4). To get the fibonancci of 5, we have evaluate F(4) and F(3). This means we have to compute F(4) twice: one for F(5) and the other for F(6). Since there are a lot of repeated computation, we can use a dictionary to store our result and fetch it instead of just repeating the process  
>
Code
```python
def checker(n):
    memo = {}
    def fibonacci(n):
        if n in memo:
            return memo[n]
        if n == 0 or n == 1:
            memo[n] = n
            return n
        else:
            memo[n] = fibonacci(n-1) + fibonacci(n-2)
        return memo[n]
    return fibonacci(n)

class Solution:
    def fib(self, n: int) -> int:
        if __name__ == '__main__':
            return checker(n)
```
