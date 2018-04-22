## 问题分析:
给定一个数组nums，写一个函数将所有的值移动0到最后，同时保持非零元素的相对顺序不变.
## 编程实现:
``` c++
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
          int length = nums.size();  
        int j = 0;  
        for(int i = 0; i < length; i ++)  
        {  
            if(nums[i]) {  
                nums[j ++] = nums[i];  
            }  
        }  
        for(int i = j; i < length; i ++)  
            nums[i] = 0;  
    }  
    
};
```
## 总结体会:
记录一个下标，对数组进行遍历，当非0时，将该数置于该下标内，并将下标值+1，最终从下标到数组尾全部置0.
