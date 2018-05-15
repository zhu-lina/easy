 ## 问题分析：
给定一个正整数，检查它是否有交替位：即，如果两个相邻位总是有不同的值.
 ## 编程实现：
 ```c++
 class Solution {
public:
    bool hasAlternatingBits(int n) {
     int temp=-1;  
    while(n!=0)  
    {  
        if(temp==n%2)  
        {  
            return false;  
        }  
        else  
        {  
            temp=n%2;  
            n=(n-temp)/2;  
        }  
    }  
    return true;      
    }
};
 ```
 ## 总结体会：
正整数主要是看二进制位是否为交替变化的，如果是的话，输出true，否则为false。