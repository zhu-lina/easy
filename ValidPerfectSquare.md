## 问题分析： 
给定一个正整数num，写一个函数返回True，如果num是一个完美的平方，否则为False。
## 编程实现：
```c++
class Solution {
public:
    bool isPerfectSquare(int num) {
          if(num < 1) 
              return false;  
        if(num == 1) 
            return true;  
        int left = 0, right = num/2;  
        while(left <= right)  
        {  
            long mid = (left+right)/2;  
            long val = mid*mid;  
            if(val == num) 
                return true;  
            else if(val > num)
                right = mid-1;  
            else left = mid+1;  
        }  
        return false;  
    }  
};   
   
```
## 总结体会：
利用二分法思想进行查找，然后在用val值和num进行比对，找出完美的平方。