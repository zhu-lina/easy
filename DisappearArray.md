## 问题分析：
给定一个整数数组，其中1≤a[i]≤n（n =数组的大小），一些元素出现两次，其他元素出现一次。查找[1，n]的所有元素，这些元素不出现在这个数组中。
## 编程实现：
```c++
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        int l=nums.size();  
        vector<int> temp(l,0);  
        vector<int> result;  
        for(int i=0;i<l;i++){  
            temp[nums[i]-1]=-1;  
        }  
        for(int i=0;i<l;i++){  
            if(temp[i]==0)  
               result.push_back(i+1);  
        }  
        return result;  
    }
};
```
## 总结体会：
定义一个长度为n的数组temp，全都初始化为0。然后遍历给出的数组，令temp[nums[i]-1]=-1。最后遍历数组temp，那些值为0的数的位置加上1就是所要求的没有出现的数。