## 问题分析：
我们有两个特殊字符。 第一个字符可以用1位表示。第二个字符可以用2位表示（10或11）。
现在给出一个由几位表示的字符串。 返回最后一个字符是否必须是一位字符。 给定的字符串将始终以零结尾。
## 编程实现：
```c++
 class Solution {
public:
    bool isOneBitCharacter(vector<int>& bits) {
         int n = bits.size(), i = 0;
        while (i < n - 1) {
            if (bits[i] == 0) i++;
            else i += 2;
        }
        return i == n - 1 ? true : false;
    }
};
```
## 总结体会：
从头到尾遍历，如果该位数字为1，则向后前进两位，否则前进1位。