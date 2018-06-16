## 问题分析：
给定一个整数数组和整数k，您需要在数组中找到唯一的k-diff对的数量。 这里k-diff对被定义为一个整数对（i，j），其中i和j都是数组中的数字，它们的绝对差值是k。
## 编程实现：
```c++
class Solution {
public:
    int findPairs(vector<int>& nums, int k) {
        sort(nums.begin(),nums.end());  
    int ans=0;  
    for(int i=0,j=1;i<nums.size();i++)  
    {  
        j=max(j,i+1);  
        while(j<nums.size()&&nums[j]-nums[i]<k){  
            j++;  
        }  
        if(nums[j]-nums[i]==k)ans++;  
        while(i+1<nums.size()&&nums[i]==nums[i+1])i++;  
    }  
    return ans;  
    }
};
```
## 总结体会：
两指针，排序后；两指针同时遍历注意j必须大于i还有题目的唯一性必须跳过相同元素。