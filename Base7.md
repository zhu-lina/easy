## 问题分析：
给定一个整数，将数字转化为7进制，用字符串形式输出。
## 编程实现：
```c++
class Solution {
public:
    string convertToBase7(int num) {
        if (num==0) 
            return "0";
        bool flag = (num>0)?true:false;
        num = (num>0)?num:num*(-1);
        string res;
        int tmp;
        while (num!=0)
        {
            tmp = num%7;
            num /= 7;
            res =  to_string(tmp)+res;
        }
        if (!flag)
            res = string(1, '-')+res;
        return res; 
    }
};
```
## 总结体会：
将十进制数字转换成7进制，且以字符串形式返回。若数字为负数，则将其绝对值转换后再添加符号。