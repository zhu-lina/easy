## 问题分析：
给出一个字符串s，计算具有相同数量0和1的非空（连续）子字符给定一个非空数组，返回此数组中的第三个最大数。 如果不存在，则返回最大数量。 时间复杂性必须在O（n）中。串的数量，并且这些子字符串中的所有0和1都连续分组。多次出现的子串被统计为它们发生的次数。
## 编程实现：
```c++
class Solution {
public:
    int thirdMax(vector<int>& nums) {
         long Max = LONG_MIN, secMax = LONG_MIN, thirdMax = LONG_MIN;  
        for(auto num: nums)  
        {  
            if(num > Max)  
            {  
                if(secMax!=LONG_MIN) thirdMax = secMax;  
                if(Max!=LONG_MIN) secMax = Max;  
                Max = num;  
            }  
            else if(num > secMax && num!= Max)  
            {  
                if(secMax!=LONG_MIN) thirdMax = secMax;  
                secMax = num;  
            }  
            else if(num > thirdMax && num!= Max && num!=secMax) thirdMax = num;  
        }  
        return thirdMax==LONG_MIN?Max:thirdMax;  
    }
};
```
## 总结体会：
保存三个变量代表最大的三个数，并且三个数必须是不同的．每次先更新最大的数，如果可以更新，还要看是否能进行转移，也就是原来最大的数变为第二大的数，原来第二大的数变为第三大的数．然后在比较如果当前数比最大数小是否比第二大的数大,依次，如果最后没有第三大的数就返回最大的数。