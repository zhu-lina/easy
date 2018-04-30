## 问题分析：
给定一个整数，写一个函数来确定它是否为3的幂。
## 编程实现：
```c++
class Solution {
public:
    bool isPowerOfThree(int n) {
          if (n == 0)
      return false;
    else if (n == 1)
      return true;

    else if (n%3==0)
         return isPowerOfThree(n/3);
    else
       return false;
}
    
};

```
## 总结体会：
采用了if-else语句，先把整数0输出为false和1输出为true直接返回，然后再寻找一个整数是否为3的幂。

 