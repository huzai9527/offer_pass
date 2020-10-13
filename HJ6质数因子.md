## 题目描述
功能:输入一个正整数，按照从小到大的顺序输出它的所有质因子（重复的也要列举）（如180的质因子为2 2 3 3 5 ）最后一个数后面也要有空格

- 最近感觉脑子不行了,本来很简单的一道题,想复杂了
- 顺便复习了快速幂、费马小定理(素数判定)
### 本题思路
- 任何数都能分解为n个质数相乘
- 并且可以直接取余判断,因为能被4,6,8...除的2都能; 同样的能被6,9,12..除的3都能
- 因此只要从小到大依次判断即可
```python
def resolve_n(n):
    rst = []
    while n!=1:
        #这里注意n+1,不然取不到n,会死循环,两次栽了
        for i in range(2,n+1):
            if n % i == 0:
                n = n//i
                rst.append(i)
                break
    return rst
  

```

### 快速幂取模
```pyhton
def quick_pow(a, u, n):
    ans = 1
    while u:
        if u % 2 == 1:
            ans = ans * a % n
        a = a * a % n
        u = u // 2
    return ans
```

### 素数判定(费马小定理)

```python
def is_primer(n):
    tmp = [2,3,5,7]
    flag = 1
    if n in tmp:
        return True
    for i in range(len(tmp)):
        if quick_pow(tmp[i], n-1, n) != 1:
            flag = 0
            break
    if flag:
        return True
    return False
```

### n以内的素数

```python
def n_primer(n):
    rst = []
    for i in range(2, n):
        if is_primer(i):
            rst.append(i)
    return rst
```
