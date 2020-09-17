## 题目描述
输入一个递增排序的数组和一个数字S，在数组中查找两个数，使得他们的和正好是S，如果有多对数字的和等于S，输出两个数的乘积最小的。
- 由于数组是递增的，因此从头遍历,找到符合 s-array[i] 任然在数组中的数即可
```python
class Solution:
    def FindNumbersWithSum(self,array, tsum):
        res = []
        for i in range(len(array)):
            if (tsum - array[i]) in array:
                res.append(array[i])
                res.append(tsum-array[i])
                break
        return res
```
