## 问题分析：
给定一个词，你需要判断首都的用法是否正确。
## 编程实现：
```c++
class Solution {
public:
    bool detectCapitalUse(string word) {
    if(word[0]>=97){
            for(int i=1; i<word.length(); i++){
                if(word[i]>=97){
                    continue;
                }else return false;
            }
        }else{
            if(word[1]>=97){
                for(int i=2; i<word.length(); i++){
                    if(word[i]>=97){
                        continue;
                    }else return false;
                }
            }else{
                for(int i=2; i<word.length(); i++){
                    if(word[i]<97){
                        continue;
                    }else return false;
                }
            }
        }
        return true;
    }
};
```
## 总结体会：
如果第一个字母小写，后面都是小写则符合条件，否则不符合条件；如果第一个字母大写，这里分两种情况，
如果第二个字母为大写，那么其后面的字母都应该是大写才可符合条件；如果第二个字母为小写，后面的字
母就应该是小写才符合条件，否则其余的都不符合条件。