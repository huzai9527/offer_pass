## 一只青蛙一次可以跳上1级台阶，也可以跳上2级。求该青蛙跳上一个n级的台阶总共有多少种跳法（先后次序不同算不同的结果）。

- 首先f[n]的可能次数是由f[n-1]向上跳一级或者f[n-2]向上跳两级得到，既f[n]=f[n-1]+f[n-2],明显的f[1]=1,f[2]=2，由递归得：
```pyhton
class Solution:
    def jumpFloor(self, number):
        if number == 2:
            return 2
        if number == 1:
            return 1
        else:
            return self.jumpFloor(number-1)+self.jumpFloor(number-2)
```

- 用递归算法有可能出现超时，而一般的递归问题得到关于**状态的表达式**即可用动态规划解决，因此有：
```python
# -*- coding:utf-8 -*-
class Solution:
    def jumpFloor(self, number):
        dp = [0 for i in range(45)]
        dp[0] = dp[1] = 1
        for i in range(2,45):
            dp[i] = dp[i-1]+dp[i-2]
        return dp[number]
```
