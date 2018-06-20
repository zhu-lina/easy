## 问题分析：
假设你有一个长的花坛，其中一些地块种植，一些不是。 然而，鲜花不能在相邻的地块种植，它们会争夺水分，两者都会死亡。给定一个花坛（表示为包含0和1的数组，其中0表示空，1表示不为空）以及数字n，如果可以种植n朵新鲜花而不违反无邻近花的规则，则返回。
## 编程实现：
```c++
class Solution {
public:
    bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        int len = flowerbed.size();
        int num = 0;
        for (int i = 0; i < len; i +=2) {
            if (flowerbed[i] == 0) {
                if ( (i+1 >=len ||flowerbed[i + 1] == 0) && (i-1 < 0 ||flowerbed[i - 1] == 0) ) num++;
            }
        }
        if (num >= n) return true;
        num = 0;
        for (int i = 1; i < len; i += 2) {
            if (flowerbed[i] == 0) {
                if ((i+1 >= len || flowerbed[i + 1] ==0) && (i-1 < 0 || flowerbed[i - 1] == 0)) num++;
            }
        }
        if (num >= n) return true;
        return false;
    }
};
```
## 总结体会：
采用枚举法解决该问题，利用了if语句和for循环语句进行判断。