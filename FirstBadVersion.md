## 问题分析：
假设有n个版本[1,2，...，n]，并且你想找出第一个错误的版本，这会导致下面所有的错误。
给一个API布尔isBadVersion（版本），它将返回版本是否坏。 实现一个函数来查找第一个错误版本。您应该尽量减少对API的调用次数。
## 编程实现：
```c++
bool isBadVersion(int version);

class Solution {
public:
    int firstBadVersion(int n) {
         int start = 1,end =n,mid=1;
          while(start + 1 <end){
             mid = start + (end - start)/2;
              if(isBadVersion(mid)){
                 end = mid;
             }else{
                start = mid;
            }
         }
         if(isBadVersion(start)){
             return start;
         }
         return end; 
    }
};
```
## 总结体会：
主要采用二分法查找思想。