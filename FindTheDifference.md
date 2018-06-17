## 问题分析：
给定两个字符串s和t，它们只包含小写字母。字符串t由随机洗牌字符串s生成，然后在随机位置再添加一个字母。找到在t中添加的字母。
## 编程实现：
```c++
class Solution {
public:
    char findTheDifference(string s, string t)
    {
         int ans = 0, i, lens = s.length(), lent = t.length();
        for(i = 0; i < lens; i++)
            ans ^= (s[i] - 'a');
         for(i = 0; i < lent; i++)
             ans ^= (t[i] - 'a');
         return 'a' + ans;
    }
    
};
```
## 总结体会：
利用异或运算,两个字符串加起来只有一个字符时单独的。