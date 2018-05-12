## 问题分析：
给定一个大小为n的非空整数数组，找到使所有数组元素相等所需的最小移动次数，其中移动将n-1个元素递增1。
## 编程实现：
```c++
class Solution {
public:
    int minMoves(vector<int>& nums) {
        int min = nums[0];
        int sum = 0;
        for (int i = 0; i < nums.size(); i++) {
            sum += nums[i];
            if (min > nums[i]) {
                min = nums[i];
            }
        }
        return sum - nums.size() * min;
    }
};
```
## 总结体会：
每个数都加一后其中一个数减一，那么要让每个数相等，最终就会是每个数都等于最小的那个数。
那么要求最小次数就是每个数减去最小数，再求和。

