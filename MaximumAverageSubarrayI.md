## 问题分析：
给定一个由n个整数组成的数组，找到具有最大平均值的给定长度k的连续子数组。 你需要输出最大的平均值。
## 编程实现：
```c++
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
         int  result, sum = 0;

        for (int i = 0; i < k; i++)
            sum += nums[i];
        result = sum;

        for (int i = 1; i <= nums.size() - k; i++){
            sum = sum - nums[i - 1] + nums[i + k - 1];
            result = max(sum, result);
        }

        return (double)result / k;
    }
};
```
## 总结体会：
由于数组中存储的是整数，所以直接拿和除以k得到的数字还是整数，要对求得的和进行强制类型转换。平均数最大等价于和最大，所以中途运算是不需要算平均数，只需要在最后结果处除以k。