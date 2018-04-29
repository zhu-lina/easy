## 问题分析：
给出一组有序数组和一个目标数字，求目标数字在数组中的位置，没找到时则求插入数组的位置.
## 编程实现：
```c++
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {  
        int length = nums.size();
        int left = 0;
        int right = length - 1;
        int index = left;
        while (left <=right) {
            int mid = left+(right-left) / 2;
            if (target > nums[mid]) {
                left = mid + 1;
                index = left;
            } else if (target < nums[mid]) {
                right = mid - 1;
                index = mid;
            } else if(target==nums[mid]) {
                return mid;
            }
        }
        return index;
    }
};
```
## 总结体会：
采用二分法的思想，其值与目标值大小进行比对，然后根据大小调整左右值，再返回索引.

 