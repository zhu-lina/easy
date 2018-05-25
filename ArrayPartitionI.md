## 问题分析：
给定一个2n整数的数组，你的任务是把这些整数分成n对整数，比如（a1，b1），（a2，b2），...，（an，bn），这使得min（ai， bi）对于所有我从1到n尽可能大。
## 编程实现：
```c++
class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
         int res = 0;
        sort(nums.begin(), nums.end());
        for (int i = 0; i < nums.size(); i++){
            if (i % 2 == 0){
                res += nums[i];
            }
        }
        return res; 
    }
};
```
## 总结体会：
找出配对后最小值的和的最大值，要求最小值要与另一个数的差值最小，这样最小值才有机会获得更大的值，让每个配对的数中较大值取为较小值的后一个数。