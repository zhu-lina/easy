## 问题分析： 
给定已按升序排序的整数数组，找到两个数字，使它们合计为特定的目标数字。
函数twoSum应该返回这两个数字的索引，以便它们合计到目标，其中index1必须小于index2.
## 编程实现：
```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
          vector<int> indexes;
        int left = 0;
        int right = numbers.size() - 1;
        int sum = 0;

        while(left < right) {
            sum = numbers[left] + numbers[right];
            if (sum == target) {
                indexes.push_back(left + 1);
                indexes.push_back(right + 1);
                break;
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }

        return indexes;
    }
    
}; 
   
```
## 总结体会：
本题的关键是sum>target,说明右指针指向的元素过大，所以向左移动右指针。sum<target,说明左指针指向的元素过小，所以向右移动左指针。
sum=target,找到了和为target的两个数的索引，返回这两个索引。