## 问题分析：
计算字符串中段的数量，其中段定义为非空格字符的连续序列。
请注意，该字符串不包含任何不可打印的字符。
## 编程实现：
```c++
class Solution {
public:
    int countSegments(string s) {
          int l=s.length();
        int result=0;
        for(int i=0;i<l;i++){
            if(s[i]==' ')
                continue;
            result++;
            while(i<l && s[i]!=' ') 
                ++i;
        }
        return result;
    }
};
```
## 总结体会：
遍历字符串。遇到空格跳出，遇到一个字符，统计值加1，然后用while循环找接下来空字符的位置。 