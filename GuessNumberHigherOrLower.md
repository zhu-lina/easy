## 问题分析：
我们正在玩猜数游戏。 游戏如下： 
我从 1 到 n 选择一个数字。 你需要猜我选择了哪个号码。 
每次你猜错了，我会告诉你这个数字是高还是低。 
你调用一个预定义的接口 guess(int num)，它会返回 3 个可能的结果(-1，1或0):
## 编程实现：
``` c++
int guess(int num);

class Solution {
public:
    int guessNumber(int n) {
       
        int lower = 1, higher = n;  
        while(lower <= higher)  
        {  
            int mid =lower+(higher-lower)/2, c = guess(mid);  
            if(c == 0) return mid;  
            else if(c == -1)
                 higher=mid-1;
            else if(c == 1)
                  lower=mid+1;
        }  
       
    }   
    
};
```
## 总结体会：
采用二分法的思想，先找到中间值，再根据调用的预定义guess(mid)返回-1,1,0进行调整.