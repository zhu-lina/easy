## 问题分析：
给定一个罗马数字，将其转换为整数。输入的范围从1到3999。
## 编程实现：
```c++
class Solution {
public:
    int romanToInt(string s) {
      int sum=0;  
        int length = s.size();  
        map<char,int> myMap;  
        myMap['I']=1;  
        myMap['V']=5;  
        myMap['X']=10;  
        myMap['L']=50;  
        myMap['C']=100;  
        myMap['D']=500;  
        myMap['M']=1000;   
        int i=0;  
        int j;  
        while( i <length )  
        {  
            while(i<length&&myMap[s[i]] >= myMap[s[i+1]])  
            {  
                sum = sum + myMap[s[i]];  
                i++;  
            }  
            while(i<length&&myMap[s[i]] < myMap[s[i+1]])  
            {  
                sum = sum - myMap[s[i]];  
                i++;  
            }  
                  
        }  
        return sum;  
    }
};
```
## 总结体会：
在罗马数字转换整数的过程中，其关键是小的数字在大的数字的右边，所表示的数等于这些数字相加得到的数，反之相减。