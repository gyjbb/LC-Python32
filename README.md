# LC-Python32
Dynamic planning 1


## Theory, 509.Fibonacci Number, 70.Climbing Stairs, 746.Min Cost Climbing Stairs
July 05, 2023  4h

Congratulations!\
This is the 32th day for leetcode python study. Today we will learn about the Dynamic planning!\
The challenges today are especially about Fibonacci Number and climbing steps. Learn the 5 steps of dynamic planning and how to find the hook formula. 

## Theory
DP array dp[i][j] and meaning of indexes, hook formula, initialization, order of iteration, print the dp array. These are the 5 steps of dynamic planning. 


## 509.Fibonacci Number
```python
class Solution:
    def fib(self, n: int) -> int:
        if n == 0:
            return 0
        dp = [0] * (n+1)        #create dp table
        dp[0] = 0       #initialize dp array
        dp[1] = 1       
        for i in range(2, n+1):     #the order of iteration
            dp[i] = dp[i-1] + dp[i-2]       #the hook formula

        return dp[n]        #return the result
```


## 70.Climbing Stairs
This question is similar to the fibonacci number.
```python
class Solution:
    def climbStairs(self, n: int) -> int:
        if n <= 1:
            return n
        
        dp = [0] * (n+1)
        dp[1] = 1
        dp[2] = 2

        for i in range(3, n+1):
            dp[i] = dp[i-1] + dp[i-2]

        return dp[n]
```


## 746.Min Cost Climbing Stairs
The first step cost nothing. To reach the next step, it costs costs[i]. \
We define dp[i] as the minimum cost to reach step i. So dp[i] can either be dp[i-1]+cost[i-1] or dp[i-2]+cost[i-2] since we can walk one/two steps per time. Then we get the minimum of the two solutions for dp[i].\
Attention here, dp[0] is 0, and dp[1] is also 0, because the question said we can start from either step 0 or step 1, and jumping to these two steps takes no effort, and with no cost. But jumping from 0/1 step to 2 or higher steps will have costs.\
In the following picture, we can see why in the iteration, we loop from 2 until len(cost)+1.\
<img src="https://github.com/gyjbb/LC-Python32/blob/main/IMG_C7188E229B74-1.jpeg" width="300" height="250">

```python
class Solution:
    def minCostClimbingStairs(self, cost: List[int]) -> int:
        dp = [0] * (len(cost)+1)
        dp[0] = 0
        dp[0] = 0

        for i in range(2, len(cost)+1):   
            dp[i] = dp[i] = min(dp[i - 1] + cost[i - 1], dp[i - 2] + cost[i - 2])
        
        return dp[len(cost)]        #return the minimum cost to reach the top
```

