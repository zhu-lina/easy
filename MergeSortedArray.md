## 问题分析：
给定两个排序的整数数组nums1和nums2，将nums2合并为nums1作为一个排序数组。
## 编程实现：
```c++
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i1 = m - 1, i2 = n - 1, k = m + n - 1;
         while (i1>= 0 && i2>=0){
              if (nums1[i1] < nums2[i2])
              {
                  nums1[k--] = nums2[i2--];
              }
             else{
                 nums1[k--] = nums1[i1--];
             }
         }
         while (i2 >= 0){
             nums1[k--] = nums2[i2--];
         }
          return;
    }
};
```
## 总结体会：
利用好nums1后n个空闲的空间是关键。