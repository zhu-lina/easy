## 问题分析：
给定一个非空字符串检查是否可以通过获取它的一个子字符串并将多个子字符副本附加在一起来构造它。 你可能会认为给定的字符串只包含小写英文字母，其长度不会超过10000。
## 编程实现：
```c++
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
      int length = s.size();
          for (int i = 1; i <= length / 2; i++) {
             if (length % i == 0) {
                 string sub = s.substr(0, i);
                 
                 int j;
                  for (j = 1; j < length / i; j++) {
                      if (sub != s.substr(i * j, i)) {
                         break;
                     }
                 }
                 
                 if (j == length / i)
                     return true;
             }
         }
         
         return false;  
    }
};
```
## 总结体会：
首先通过所给字符串长度枚举出可以作为重复子串的字符串长度，在每个枚举中，分别判断是否满足题意。