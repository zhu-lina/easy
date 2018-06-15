## 问题分析：
给定一个整数n，返回n！中尾随零的数量。
## 编程实现：
```c++
class Solution {
public:
    int trailingZeroes(int n) {
       int count = 0;  
        while(n>0){  
            int k = n/5;  
            count+=k;  
            n=k;  
        }  
        return count;    
    }
};
```
## 总结体会：
阶乘 n! 末尾0的个数是由其中因数2和因数5的个数决定。因此，我们只需求出因数2的个数和因数5的个数，取其中最小值就是我们所要的值。总结起来就是计算n/5，n/5/5，n/5/5/5，...直到商为0。