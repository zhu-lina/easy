## 问题分析：
给定一个有序的数组nums，删除重复内容，使每个元素只出现一次并返回新的长度。
## 编程实现：
```c++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
         if(nums.empty())
        {
            return 0;
        }
        int n = nums.size();
        if(n == 1)
        {
            return 1;
        }
        int sum = 1;
        int j = 0;
        for(int i = 1; i < n; i++)
        {
            if(nums[j] != nums[i])
            {
               nums[j+1] = nums[i];
               sum++;
               j++;
            }
            
        }
        return sum;
    }
};
```
## 总结体会：
对排好序的数列去重。返回不重复的数的个数n，并将其一次排列在原来数组的前n位。