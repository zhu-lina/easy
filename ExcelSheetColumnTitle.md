## 问题分析：
给定一个正整数，返回它在Excel工作表中出现的相应的列标题。
## 编程实现：
```c++
class Solution {
public:
    string convertToTitle(int n) {
         string ret = "";
        while(n)
        {
            ret = (char)((n-1)%26+'A') + ret;
            n = (n-1)/26;
        }
        return ret;
    }
};
```
## 总结体会：
将一个10进制数转换为一个26进制的数，由于下标从1开始而不是从0开始，要减一操作。