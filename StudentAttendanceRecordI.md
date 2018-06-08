## 问题分析：
给你一个代表学生出勤记录的字符串。 该记录只包含以下三个字符：
'A'：缺席。
'L'：晚了。
'P'：现在。
如果他的出勤记录不包含多于一个“A”（缺席）或超过两个连续的“L”（晚），则可以奖励学生。
你需要根据他的出勤记录来回报学生是否可以得到奖励。
## 编程实现：
```c++
class Solution {
public:
    bool checkRecord(string s) {
    int size = s.size();  
    int L = 0;  
    int A = 0;  
    for (int i = 0 ; i < size ; ++i) {  
        if (s[i] == 'A') {  
            ++A;  
            L = 0;  
        } else if (s[i] == 'L') {  
            ++L;  
        } else {  
            L = 0;  
        }  
        if (A > 1 || L > 2) return false;  
    }  
    return true;  
      }
    
};
```
## 总结体会：
计算A字符串出现的个数和计算连续的L的个数。当A的个数超过1个，连续L的个数超过2个时，输出False。