## 题目描述
输入n个整数，找出其中最小的K个数。例如输入4,5,1,6,2,7,3,8这8个数字，则最小的4个数字是1,2,3,4。

- 排序就完事了
- 要注意当K大于数组长度时返回为空
```python 
class Solution:
    def GetLeastNumbers_Solution(self, tinput, k):
        if k>len(tinput):
            return []
        tinput.sort()
        return tinput[:k]
```

- 估计这题的本意是想让我们写个排序算法,下面给二分排序
 ```python
 def Bsort(tin):
    if len(tin)==1:
        return tin
    else:
        m = len(tin)//2
        left = Bsort(tin[:m])
        right = Bsort(tin[m:])
    merged = []
    while left and right:
        if left[0]<=right[0]:
            merged.append(left.pop(0))
        else:
            merged.append(right.pop(0))
    merged.extend(left if left else right)
        
    return merged
 ```
