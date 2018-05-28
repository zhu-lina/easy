## 问题分析:
给你两个数组（没有重复）nums1和nums2，其中nums1的元素是nums2的子集。 在相应的nums2位置查找nums1的所有元素。
nums1中数字x的下一个较大数字是nums2中右边第一个较大数字。 如果不存在，则输出-1。
## 综合实现：
```c++
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& findNums, vector<int>& nums) {
       vector<int> res;
        for (int a : findNums)
        {
            int i = 0;
            for (i = 0; i < nums.size(); i++)
            {
                if (nums[i] == a)
                    break;
            }
            for (i=i+1; i < nums.size(); i++)
            {
                if (nums[i] > a)
                    break;
            }
            res.push_back(i >= nums.size() ? -1 : nums[i]);
        }
        return res; 
    }
};
```
## 总结体会：
寻找在原数组中右边比自己大的元素，假如不存在返回-1。