## 大家都知道斐波那契数列，现在要求输入一个整数n，请你输出斐波那契数列的第n项（从0开始，第0项为0，第1项是1）。n<=39

```c++
class Solution {
public:
    int Fibonacci(int n) {
        if(n==0){
            return 0;
        }
        else{
            if(n==1||n==2){
                return 1;
            }
            else{
                return Fibonacci(n-1)+Fibonacci(n-2);
            }
        }
    }
};
```
- 主要找到停止点，以及递归表达式；python采用递归有超时情况，可以采用累加

```python
class Solution:
    def Fibonacci(self, n):
        if n==0:
            return 0
        if n==1 or n==2:
            return 1
        a = b = 1
        for i in range(2,n):
            a,b = b, a+b
        return b
 ```
