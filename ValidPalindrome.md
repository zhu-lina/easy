## 问题分析：
给定一个字符串，确定它是否是回文，只考虑字母数字字符并忽略情况。
## 编程实现：
```c++
class Solution {
public:
    bool isPalindrome(string s) {
         string str = "";
        int len = s.length();
        int lenStr = 0;
        for(int i = 0; i < len; i++){
            if((s[i] >= 'a' && s[i] <= 'z') || (s[i] >= '0' && s[i] <= '9')){
                str += s[i];
                lenStr++;
            } else if(s[i] >= 'A' && s[i] <= 'Z'){
                str += (s[i] - 'A' + 'a');
                lenStr++;
            }
        }
        for(int i = 0; i < lenStr / 2; i++){
            if(str[i] != str[lenStr - i - 1]){
                return false;
            }
        }
        return true;
    }
};
```
## 总结体会：
遍历字符串，将数字和字母提取出来一个新的字符串，然后遍历新的字符串来判断是否是回文串。

