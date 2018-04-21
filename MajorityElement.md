## 问题分析：
给定一个大小为n的数组，找到多数元素。多数元素是出现超过n/2倍的元素。您可以假定数组非空，并且多数元素始终存在于数组中。
##  编程实现：
``` c++
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        
        int count=0;
        int result=nums[0];
        for(int i=0;i<nums.size();i++)
        {
            if(count==0||nums[i]==result)
            {
                count++;
                result=nums[i];
            }
            else
                count--;
        }
        return result;
    }};
```
## 总结体会：
将数组中的数两两进行对比，看其是否相等，若相等，则计数加1.若不等，则计数减1.还利用了for循环语句.