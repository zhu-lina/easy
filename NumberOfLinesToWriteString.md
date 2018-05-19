## 问题分析：
我们将给定字符串S的字母从左到右写入行中。 每行的最大宽度为100个单位，如果写入一个字母会导致该行的宽度超过100个单位，则会将其写入下一行。 宽度[0]是'a'的宽度，widths [1]是'b'的宽度，...，widths [25]是'z'的宽度，。
## 编程实现：
```c++
class Solution {
public:
    vector<int> numberOfLines(vector<int>& widths, string S) {
         int cnt=0,wid=0;                
        for(int i=0;i<S.size();){
            if(wid+widths[S[i]-'a']>100){  
                cnt++;
                wid=0;
            }
            else{
                wid+=widths[S[i]-'a'];  
                i++;
            }
        }

        return {++cnt,wid};             
    }
};
```
## 总结体会：
每次先判断输出新字符会不会超过了改行要求的长度，如果超过了，那么行数++，把记录当前行已输出字符长度的wid置为0.