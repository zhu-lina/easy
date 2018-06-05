## 问题分析：
总共有n个硬币需要形成阶梯状，每个第k行必须有k个硬币。
## 编程实现：
```c++
class Solution {
public:
    int arrangeCoins(int n) {
        if (n <= 1) return n;
        long low = 1, high = n;
        while (low < high) {
            long mid = low + (high - low) / 2;
            if (mid * (mid + 1) / 2 <= n) low = mid + 1;
            else high = mid;
        }
        return low - 1;
    }
};
```
## 总结体会：
用到了二分法，搜索前i行之和刚好大于n的临界点，这样我们减一个就是能排满的行数，注意我们计算前i行之和有可能会整型溢出，所以我们需要将变量都定义成长整型。