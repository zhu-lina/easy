 ## 问题分析：
 给定两个以字符串表示的非负数整数num1和num2，返回num1和num2的总和。
 ## 编程实现：
 ```c++
 class Solution {
public:
    string addStrings(string num1, string num2) {
          string num;
        int length1 = num1.length();
        int length2 = num2.length();
        int result = 0;

        for ( int i = length1 - 1, j = length2 - 1; i >= 0 || j >= 0; --i, --j)
        {
            int temp = 0;
            if (i >= 0)
            {
                temp += num1[i] - '0';
            }
            if (j >= 0)
            {
                temp += num2[j] - '0';
            }
            if (result)
            {
                ++temp;
            }
            result = temp / 10;
            temp = temp % 10;

            num = char(temp + '0') + num;
        }
        if (result)
        {
            num = char(result + '0') + num;
        }

        return num;
    }
};
 ```
 ## 总结体会：
 首先算出两个字符串的长度，并从两个字符串的最后一个字符开始循环，两个字符串对应位置的值相加，若有进制，则保存。若某一字符串的长度较长，需要将该字符串剩下的字符遍历完成