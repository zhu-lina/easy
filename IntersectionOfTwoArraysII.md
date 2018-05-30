## 问题分析：
给定两个数组，写一个函数来计算它们的交集。
## 编程实现：
```c++
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
         vector<int> res;
          int length1 = nums1.size(), length2 = nums2.size();
          sort(nums1.begin(), nums1.end());
          sort(nums2.begin(), nums2.end());
         int i = 0, j = 0;
         while (i < length1 && j < length2) {
             if (nums1[i] < nums2[j]) {
                i++;
             }
             else if (nums1[i] > nums2[j]) {
                 j++;
            }
             else {
                 res.push_back(nums1[i]);
                 i++;
                 j++;
             }
         }
         
         return res;
     }
 };
```
## 总结体会：
首先将两个数组从小到大排序，后分别用两个指针指向两个数组开头比较大小，将小的数组指针后移。直至两指针指向数字相等时考虑将数字放入res中。