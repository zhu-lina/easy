## 问题分析：
我们定义完美的数是一个正整数它等于除了它本身的所有正因数的和。现在，给定一个整数n，写一个函数，当它是一个完美的数字时，它会返回true，而当它不是时，它会返回false。
## 编程实现：
``` c++
class Solution {
public:
    bool checkPerfectNumber(int num) {
         if(num==1) return false;  
        int sum=0;  
        for(int i=2;i<sqrt(num);i++)  
         if(num%i==0)  
         {
            sum+=i;  
            if(i!=num/i) sum+=num/i;  
        }  
        sum++;  
        return sum==num;  
    }  
};
```
## 总结体会：
在考虑完美数时，首先考虑数为1的情况下返回false值，然后利用for循环和if语句来寻找正因数以及求和，最终判断是否为完美数.
