## 问题分析：
给定一个整数数组nums，编写一个返回该数组的“pivot”索引的方法。
我们将pivot索引定义为索引左边的数字总和等于索引右边数字总和的索引。
如果不存在这样的索引，我们应该返回-1。 如果有多个透视索引，则应返回最左侧的透视索引。
## 编程实现：
```c++
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
         int d = nums.size();  
  
        if(d == 0)  
            return -1;  
  
        int left = nums[0], right = 0;  
        for(int i = 0; i < d; i++)  
            right += nums[i];  
        if(left == right)  
            return 0;  
  
        for(int i = 1; i < d; i++)  
        {  
            left += nums[i];  
            right -= nums[i - 1];  
            if(left == right)  
                return i;  
        }  
        return -1;  
    }
};
```
## 总结体会：
从0开始，定义两个变量left 和 right分别代表轴左边的数据之和以及轴右边的数据之和，判断left是否等于right，如果相等返回下标，否则返回-1.