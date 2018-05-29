## 问题分析:
给定一个表示非负整数的非空数字数组，加上一个整数
数字被存储为使得最高有效位数位于列表头部，并且数组中的每个元素都包含一个数字。
您可以假定整数不包含任何前导零，除了数字0本身。
## 综合实现：
```c++
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
          int c = 1; 
          for(int i = digits.size() - 1; i >= 0; -- i)
         {
             int a = digits[i] + c;
             digits[i] = a % 10;
             c = a / 10;
         }
         if(c == 1)
            digits.insert(digits.begin(), 1);
         
        return digits;
    }
};
```
## 总结体会：
遍历数组的每位，同时处理进位，如果最后还有进位，则在数组最前面在插入1.