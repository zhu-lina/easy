## 问题分析：
给定一个数组和一个值val，删除该值的所有实例并返回新的长度.
## 编程实现：
```c++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
         int length = nums.size();  
        int j = 0 ;  
        for(int i = 0; i<length; i++){  
            if(nums[i] != val)  
            { nums[j] = nums[i]; 
            j++;
            }
        }  
        return  j;  
          
    }  
    
};
```
## 总结体会： 
从头开始遍历数组，若数组中元素与val不相等，则将nums[i]赋给nums[j],然后将j+1;然后执行下一次循环；若数组中元素与val值相等，则执行下一次循环直到循环执行结束；



 