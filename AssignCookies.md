## 问题分析：
假设你是一位出色的家长，并想给你的孩子一些饼干。 但是，你应该给每个孩子最多一个饼干。 每个孩子都有一个贪婪因子gi，这是孩子满足的一个曲奇饼的最小尺寸; 每个曲奇饼 j的大小为sj。 如果sj> = gi，我们可以将曲奇饼 j分配给孩子i，而孩子我会满足。 您的目标是最大化内容子项的数量并输出最大数量。
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
将两个数组由小到大排序，分别用指针从头至尾比较。