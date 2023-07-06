# LC-Python32
Dynamic planning 1


## Theory, 509.Fibonacci Number, 70.Climbing Stairs
July 05, 2023  4h

Congratulations!\
This is the 32th day for leetcode python study. Today we will learn about the Dynamic planning!\
The challenges today are especially about ~~categorizing the situation into different parts clearly~~. 


## Theory
DP array dp[i][j] and meaning of indexes, hook formula, initialization, order of iterration, print the dp array. These are the 5 steps of dynamic planning. 


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

```


## 746. 
使用最小花费爬楼梯 这道题目力扣改了题目描述了，现在的题目描述清晰很多，相当于明确说 第一步是不用花费的。 更改题目描述之后，相当于是 文章中 「拓展」的解法 

