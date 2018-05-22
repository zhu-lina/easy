## 问题分析：
给定一个整数数组，查找数组是否包含任何重复项。
如果任何值在数组中至少出现两次，则函数应该返回true，并且如果每个元素都不相同，则它应该返回false。
## 编程实现：
```c++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
     int length = nums.size();
         sort(nums.begin(), nums.end());
        for (int i = 1; i < length; i++) {
             if (nums[i] == nums[i - 1]) {
                 return true;
            }
        }         
        return false;   
    }
};
```
## 总结体会：
给数组排序后遍历，判断相邻两值是否相等。