## 问题分析：
给定两个二进制字符串，返回它们的和（也是一个二进制字符串）。输入字符串都是非空的，只包含字符1或0。
## 编程实现：
```c++
class Solution {
public:
    string addBinary(string a, string b) {
           
        string result = "";  
        int c = 0;  
        int i = a.size() - 1;  
        int j = b.size() - 1;  
          
        while(i >= 0 || j >=0 ||c ==1)  
        {  if (i >= 0)
            
          if (i >= 0)
                c= c + a[i--] - '0';
            if (j >= 0)
                c= c+ b[j--] - '0';
            result = char(c%2+'0') + result;
            c= c / 2;
              
        }  
          
        return result;  
    }
};
```
## 总结体会：
设置进位c，同时也作为每次相加的和。然后循环，条件是c==1或者两个字符串有一个没有遍历完成。然后每次c+各字符串当前坐标下的值-‘0’；最后，将c%2转换为字符加到要返回的string前面，并且c/2获取下一次的进位值。最后循环结束，返回string。