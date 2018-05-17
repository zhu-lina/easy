## 问题分析：
给定一组两个字符串，你需要找到这组两个字符串中最长的非常见子序列。
最长的不常见的子序列被定义为这些字符串之一的最长子序列，并且这个子序列不应该是其他字符串的任何子序列。
## 编程实现：
```c++
class Solution {
public:
    int findLUSlength(string a, string b) {
      if(a == b)
        return -1;
    else
        return max(a.length(),b.length());  
    }
};
```
## 总结体会：
如果两个字符串相同就返回-1，如果不相同就返回更长的字符串的长度。