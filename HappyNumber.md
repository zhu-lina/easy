## 问题分析：
编写一个算法来确定一个数字是否“开心”。
开心号码是由以下过程定义的号码：从任何正整数开始，用数字的平方和替换该号码，并重复该过程直到数字等于1（它将停留在该位置），或者它循环 在一个不包含1的循环中无休止的。这个过程以1结束的那些数字是快乐的数字。
## 编程实现：
```c++
class Solution {
public:
    bool isHappy(int n) {
       int m = 0;

        if(n == 1 || n == 7) {
            return true;
        }
        if(n < 10) {
            return false;
        }
        while(n > 0) {
            m += (n % 10) * (n % 10);
            n = n/10;
        }
        return isHappy(m);
    }
};
```
## 总结体会：
使用递归的思路，需要注意小于10的数中，1和7都是happy number，容易忽略7。