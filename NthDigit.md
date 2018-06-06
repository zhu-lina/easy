## 问题分析：
查找无限整数序列的第n位1,2,3,4,5,6,7,8,9,10,11 ...
## 编程实现：
```c++
class Solution {
public:
    int findNthDigit(int n) {
        long digit = 1, ith = 1, base = 9;  
        while(n > base*digit)  
        {  
            n -= base*(digit++);  
            ith += base;  
            base *= 10;  
        }  
        return to_string(ith+(n-1)/digit)[(n-1)%digit]-'0';  
    }
};
```
## 总结体会：
找出给定的n落在几位数的范围内，找到具体落在哪个数字，找出具体在哪一位上。