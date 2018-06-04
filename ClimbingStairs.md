## 问题分析：
你正在爬楼梯的情况。 需要n个步骤才能到达顶端。每次你可以爬1或2步。 有多少种不同的方式可以爬到顶端？
## 编程实现：
```c++
class Solution {
public:
    int climbStairs(int n) {
         if(n<=2)
        {
            return n;
        }
        int array[n+1]={0};
        array[1]=1;
        array[2]=2;
        for(int i=3;i<=n;i++)
        {
            array[i]=array[i-1]+array[i-2];
        }
        return array[n];
    }
};
```
## 总结体会：
当楼梯只有一级时，显然只有一种方法,即f(1)=1；当楼梯有两级时，显然有两种方法,即f(2)=2；当楼梯有n级时，f(n) = f(n-1) + f(n-2)；