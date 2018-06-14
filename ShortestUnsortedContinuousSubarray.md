## 问题分析：
给定一个整数数组，你需要找到一个连续的子数组，如果你只按照升序对这个子数组进行排序，那么整个数组也将按照升序排序。你需要找到最短的这样的子数组并输出它的长度。
## 编程实现：
```c++
class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
      int max=INT_MIN,min=INT_MAX;
        bool flag=false;
        for(int i=1;i<nums.size();i++)
        {
            if(nums[i]<nums[i-1])
                flag=true;
            if(flag==true)
                min=(nums[i]<min)?nums[i]:min;      
        }
        if(!flag)
        return 0;
        flag=false;
        for(int i=nums.size()-2;i>=0;i--)
        {
            if(nums[i]>nums[i+1])
                flag=true;
            if(flag==true)
                max=(nums[i]>max)?nums[i]:max;      
        }
        int r=nums.size()-1,l=0;
        for(l;l<nums.size();l++)                    
            if(nums[l]>min)
                break;
        for(r;r>=0;r--)
            if(nums[r]<max)
                break;
        return r-l+1;    
    }   
};
```
## 总结体会：
找到无序部分的最大,最小值,然后在原序列中进行比较。