## 问题分析：
给定一个32位带符号整数，一个整数的反向数字.
## 编程实现：
```c++
class Solution {
public:
    int reverse(int x) {
        int num,ans;  
        long int sum=0;  
        while(x!=0)  
        {  
            num = x%10;  
            ans = sum*10 + num;  
           if(ans/10!= sum)
               return 0;
            sum=ans; x/=10;}
            
           
            return sum;
        } 
};
```
## 总结体会：
利用while循坏语句进行判断，采用if语句如果不等的话，产生了溢出，返回0；否则继续循坏，直到输出反向数字.