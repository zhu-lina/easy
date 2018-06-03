## 问题分析：
给定一个非空字符串s，你最多可以删除一个字符。 判断你是否可以将它作为回文。
## 编程实现：
```c++
class Solution {
public:
    bool validPalindrome(string s) {
         if (s.length() <= 1)
            return true;
        int count = 0;
        int i = 0;
        int j = s.length() - 1;
        while (i<j)
        {
            if (s[i]!=s[j])
            {
                count++;
                i++;
            }
            else
            {
                i++;
                j--;
            }   
        }
        if (count < 2)
            return true;
        i = 0;
        j = s.length() - 1;
        count = 0;
        while (i < j)
        {
            if (s[i] != s[j])
            {
                count++;
                j--;
            }
            else
            {
                i++;
                j--;
            }
        }
        if (count < 2)
            return true;
        return false;
    }
};
```

## 总结体会：
如果字符串s长度为0或者1，直接返回true。要求最多只删除1个字符，那就设定count计数。如果在判断回文的循环过程中，发生不相等，则count++。最后判断count是否小于2即可。首先初始化指针i=0，j=s.length()-1。第一个循环i小于j，判断s[i]与s[j]，如果不相等，则j不动，i先往后走一个，即i++（j往前走在下一个循环中），并且count++。如果相等，则i++，j–。循环结束，如果count小于2，则返回true。进行第二个循环，循环之前，指针i=0，j=s.length()-1，count=0恢复原值。进入循环i小于j，判断s[i]与s[j]，如果不相等，则i不动，j往前走一个，即j–，并且count++。如果相等，则i++，j–。循环结束，如果count小于2，则返回true。
最后返回false。