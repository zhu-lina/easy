## 问题分析：
给定一个有n个整数的数组，你的任务是通过修改至多1个元素来检查它是否可以不减少。如果array [i] <= array [i + 1]对于每个i（1 <= i <n）成立，我们定义一个数组是非递减的。
## 编程实现：
```c++
class Solution {
public:
    bool checkPossibility(vector<int>& nums) {
        int cnt = 0;  
        for(int i = 1; i < nums.size() && cnt <=1; i++){  
            if(nums[i-1] > nums[i]){  
                cnt++;  
                if(i-2 < 0 || nums[i-2] <= nums[i])  
                    nums[i-1] = nums[i];  
                else  
                    nums[i] = nums[i-1];  
            }  
        }  
        return cnt <= 1;   
    }
};
```
## 总结体会：
遍历整个数字，如果当前数字比前面的数字小，那么这个数字是一定要改变的。进行数字的修改，直至遍历完成，如果修改次数小于等于1，那么返回true，否则返回false。

