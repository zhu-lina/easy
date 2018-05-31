## 问题分析：
给定一个未排序的整数数组，查找最长连续递增子序列(子数组)的长度。
## 编程实现：
```c++
class Solution {
public:
    int findLengthOfLCIS(vector<int>& nums) {
         int length = nums.size();
        if (length < 2){
            return length;
        }
        int max = 1;
        int count = 1;
        for (int i = 1; i < length;++i){
            if (nums[i] > nums[i - 1]){
              count++;
            }
            else{
                max = max > count ? max : count;
                count = 1;
            }
        }
        max = max > count ? max : count;
        return max; 
    }
};
```
## 总结体会：
遍历整个数组找连续最长的，分段找各个连续的最大值，如果都是连续递增的，要加一个count和max的比较。