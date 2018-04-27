## 问题分析：
确定一个整数是否为回文.当它前后读的相同时，这个整数是一个回文数.
## 编程实现：
```c++
class Solution {
public:
    bool isPalindrome(int x) {
        if (x<0)  
            return false;
          int num,ans;  
        long int sum=0,origin=x;
        while(x!=0)  
        {  
            num = x%10;  
            ans = sum*10 + num;  
           if(ans/10!= sum)
               return 0;
            sum=ans; x/=10;}
        
    if(sum == origin)  
            return true;  
        else  
            return false;
}};
```
## 总结体会：
因为负数没有回文数，所以先去除小于0的数.然后得到整数的反转数，再与初始数进行比较判断出是否为回文数.