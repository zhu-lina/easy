## 问题分析：
编写一个采用无符号整数的函数并返回它所具有的'1'位数。
## 编程实现：
```c++
class Solution {
public:
    int hammingWeight(uint32_t n) {
          int i=0;  
        while(n!=0){  
            if(n&0x1)  
              i++;  
            n=n>>1;  
        }  
        return i;  
    }  
} ;
```
## 总结体会：
其中n&1是取n的最低位，而n=n>>1是进行右移操作，去掉最低位，然后循环实现。