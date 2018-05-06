## 问题分析： 
给定一个包含从0,1,2，...，n中取出的n个不同数字的数组，找到数组中缺少的数字。
## 编程实现：
```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
           if (nums.empty())
            return 0;
        int n = nums.size();
        int sum = n*(n+1)/2;
        int real_sum = 0;
        for(int i = 0; i < n; i++) 
        {
            real_sum += nums[i];
        }
        return sum - real_sum;
    }  
    };
```
## 总结体会：
求出从0~n的累加和，减去数组整体的和，那么由于数组内每个数字不相同，其差就是缺少的那个数字。