## 问题分析：
给定一个非空的整数数组，除一个元素外，每个元素出现两次.找到单一的元素.
## 编程实现：
```c++
class Solution {
public:
    int singleNumber(vector<int>& nums) {
         int length = nums.size();  
    int result = 0 ;  
    for (int i=0; i<length; i++)  
    {  
        result ^= nums[i];  
    }  
    return result;  
    }
};
```
## 总结体会：
由于其余元素都出现了两次，通过位运算操作可找到这个只出现一次的元素.