## 题目描述
一只青蛙一次可以跳上1级台阶，也可以跳上2级……它也可以跳上n级。求该青蛙跳上一个n级的台阶总共有多少种跳法。
- 暴力解决,找清楚每一步的状态即可
- 要上n级台阶,可以是n-1再上1级,可以是n-2再上2级...
- 由此可以得到d[n] = d[n-1]+d[n-2]+...+d[0]

```python 
def jumpFloor(number):
    rst = [1,1,2]
    for i in range(3,number+1):
        rst.append(sum(rst))
    return rst[number]
```

- 继续优化
- d[n-1] = d[n-2]+d[n-3]+...+d[0] ====> d[n] = 2*d[n-1]
 ```python 
 def jumpFloor(number):
    rst = [1,1,2]
    for i in range(3,number+1):
        rst.append(2*rst[i-1])
    return rst[number]
 ```
 
 - 继续优化
 - d[n] = 2^(n-1)
 
