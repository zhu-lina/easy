## 问题分析：
给定一个整数数列，找出其中和为特定值的那两个数.你可以假设每个输入都只会有一种答案，同样的元素不能被重用.
## 编程实现：
``` c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
            vector<int> result;
        int L= nums.size();
        for (int i = 0; i < L - 1; i++) 
        {
            for (int j = i+1; j < L; j++) 
            {
                if (nums[i] + nums[j] == target) 
                {
                    result.push_back(i);
                    result.push_back(j);
                }
            }
        }
        return result;
    }
};
```
## 总结体会：
采用for循环以及if语句对整数数列的值两两求和与目标值进行比对，然后返回直到输出的两数之和等于目标值.