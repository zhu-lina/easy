## 问题分析：
给定一个由小写或大写字母组成的字符串，找出可以用这些字母构建的最长回文的长度。
这是区分大小写的，例如“Aa”在这里不被视为回文。
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
};  int len = s.size();  
        int num[200];  
        int res = 0;  
        bool flag = false;  
        memset(num,0,sizeof(num));  
        for( int i = 0; i < len; i++ ){  
            int tmp = (int)s[i];  
            num[s[i]]++;  
        }  
        for( int i = 0; i < 200; i++ ){  
            if( num[i] == 0 ){  
                continue;  
            }  
            if( num[i]%2 == 0 ){  
                res += num[i]/2;  
            }  
            else{  
                flag = true;  
                res += (num[i]-1)/2;  
            }  
        }  
        if( flag ){  
            res = res*2+1;  
        }  
        else{  
            res *= 2;  
        }  
        return res;  
```
## 总结体会：
统计串中每个字符出现的次数，可以在串的前后添加n/2个字符。同时最多可以在串的正中间添加一个字符，取决于原先串中是否含有奇数次的元素。