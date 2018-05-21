## 问题分析：
给定两个字符串s和t，编写一个函数来确定t是否是s的一个字母。
## 编程实现：
```c++
class Solution {
public:
    bool isAnagram(string s, string t) {
         if (s.empty() && t.empty())
            return true;
        else if (s.empty() || t.empty())
            return false;

        sort(s.begin(), s.end());
        sort(t.begin(), t.end());

        if (s == t)
            return true;
        else
            return false;     
    }
};
```
## 总结体会：
调用stl的排序函数sort给两个字符串s和t排序，然后比较是否相等.