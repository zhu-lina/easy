## 问题分析：
编写一个函数，在字符串数组中查找最长公共前缀字符串。如果没有公共前缀，则返回空字符串" "。
## 编程实现：
```c++
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        int i,j;  
        string result = "";  
        if (strs.size() == 0)  
            return "";  
        sort(strs.begin(), strs.end());  
        for (j = 0; j<strs[strs.size() - 1].size(); j++)  
        {  
            i = 0;  
            while (i<(strs.size() - 1) && strs[i][j] == strs[i + 1][j])  
            {  
                i++;  
            }  
            if (i == strs.size() - 1)  
            {  
                result = result + strs[i][j];  
            }  
            else  
                break;  
        }  
        return result;  
    }  
};
```
## 总结体会：
找出数组中最长串的长度，以数组的中元素串第一位开始到最长串的长度循环进行比对，对数组索引进行迭代，来比较数组串中每一个元素串从第一位开始的每一位。如果相等,将字符添加到result串中，如果不相等，立刻break;