## 问题分析：
两个整数之间的汉明距离是相应位不同的位置数。给定两个整数x和y，计算汉明距离。
## 编程实现：
```c++
class Solution {
public:
    int hammingDistance(int x, int y) {
 
      int count = 0;
 
      while (x != 0 || y != 0) {
 
        int xbit = x % 2;
        int ybit = y % 2;
 
        if(xbit != ybit) {
          count++;
        }
        x /= 2;
        y /= 2;
      }
      return count;
    }
 
};

```
## 总结体会：
把整数从十进制数转换为二进制数，然后判断两个整数每一个对应二进制位的数值是否相等。