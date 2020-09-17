## 题目描述
小明很喜欢数学,有一天他在做数学作业时,要求计算出9~16的和,他马上就写出了正确答案是100。但是他并不满足于此,他在想究竟有多少种连续的正数序列的和为100(至少包括两个数)。没多久,他就得到另一组连续正数和为100的序列:18,19,20,21,22。现在把问题交给你,你能不能也很快的找出所有和为S的连续正数序列? Good Luck!
- 暴力循环即可，对于成功的要清空tmp[],然后继续
```python
# -*- coding:utf-8 -*-
class Solution:
    def FindContinuousSequence( tsum):
        res = []
        tmp = []
        for j in range(1,tsum):
            for i in range(j,tsum):
                tmp.append(i)
                if sum(tmp) == tsum:
                    res.append(tmp)
                    tmp = []
                    break
                elif sum(tmp) < tsum:
                    continue
                else:
                    tmp = []
                    break
        return res
```
