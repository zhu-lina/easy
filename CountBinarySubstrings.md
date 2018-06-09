## 问题分析：
给出一个字符串s，计算具有相同数量0和1的非空（连续）子字符串的数量，并且这些子字符串中的所有0和1都连续分组。多次出现的子串被统计为它们发生的次数。
## 编程实现：
```c++
class Solution {
public:
    int countBinarySubstrings(string s) {
    int len = s.length();
        int cur = 1, pre = 0, res = 0;
        for (int i = 1; i < len; ++i){
            if (s[i] == s[i - 1]){
                cur += 1;
            }
            else{
                res += min(cur, pre);
                pre = cur;
                cur = 1;
            }
        }
        return res + min(cur, pre);
    }
};
```
## 总结体会：
设当前数字连续相同的为cur(1)，之前连续相同初始为pre(0)。从第二位开始，与前面的位进行比较，如果从第二位起和之前相同，那么cur+1；否则，结果加上cur和pre中的小的那个值，并把当前的cur赋给pre，cur重置为1；最终需要加上最后一部分的cur和pre的最小值。