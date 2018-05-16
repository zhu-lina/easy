## 问题分析：
反转给定的32位无符号整数的位。
## 编程实现：
```c++
class Solution {
public:
    uint32_t reverseBits(uint32_t n) {
    uint32_t ret = 0;
    for(int i = 0; i < 32; i++)
    {
        ret = (ret << 1) + (n & 1);
        n = n >> 1;
    }
    return ret;
     }
 };   
 
```
## 总结体会：
用循环遍历各个位，然后将其放置到合适的位置。