# 剑指 Offer 04. 二维数组中的查找
***
来源： LeetCode 剑指offer
相关企业： 字节跳动
相关标签： 数组，双指针
难度： 中等
相似题型： 同主站240题
***
## 题干内容
在一个 n * m 的二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个高效的函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

 

示例:

现有矩阵 matrix 如下：


![](https://github.com/jinghehehe/pictures/blob/main/%E5%89%91%E6%8C%874.png)


给定 target = 5，返回 true。

给定 target = 20，返回 false。

 

限制：

0 <= n <= 1000

0 <= m <= 1000


来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## 题眼题解
### 题眼:
**本题是根据数组特性利用双指针来快速寻找目标数值**

- 首先从右上角开始寻找，小于target向下，大于target向左，如果出界则意味着false。
- 注意判断数组为空特殊情况。


### 题解：
#### c++版本一，时间复杂度 O(n+m), 空间复杂度 O(1)。
```language
class Solution {
public:
    bool findNumberIn2DArray(vector<vector<int>>& matrix, int target) {
        int n = matrix.size();
        if(n==0) return false;
        int m = matrix[0].size();
        int index = 0;
        int i = 0, j = m-1;
        while(i<n&&j>=0){
            if(target==matrix[i][j])
                return true;
            else if(target>matrix[i][j]){
                i++;
            }else{
                j--;
            }
        }
        return false;
    }
};
```
#### python3版本一，时间复杂度 O(n),空间复杂度 O(1)
```language
# 与c++版本一相同。
待更
```
***

### **喜欢Programming-Cat的话，请Star吧**



