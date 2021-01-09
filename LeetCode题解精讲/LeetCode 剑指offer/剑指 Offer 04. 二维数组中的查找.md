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
- 注意判断数组


### 题解：
#### c++版本一，时间复杂度 O(n+m), 空间复杂度 O(1)。
```language
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    vector<vector<int>> zigzagLevelOrder(TreeNode* root) {
        vector<vector<int> > result;
        if(root == NULL)
            return result;
        queue<TreeNode*> q;
        q.push(root);
        while(!q.empty()){
            vector<int> levelList;
            int size = q.size();
            for(int i=0; i<size; i++){
                auto p = q.front();
                q.pop();
                levelList.push_back(p->val);
                if(p->left)
                    q.push(p->left);
                if(p->right)
                    q.push(p->right);
            } 
            result.emplace_back(levelList.begin(), levelList.end());
        }
        return result;
    }
};
```
#### python3版本一，时间复杂度 O(n),空间复杂度 O(1)
```language
# 与c++版本一相同。
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def zigzagLevelOrder(self, root: TreeNode) -> List[List[int]]:
        if not root:
            return []
        q = deque()
        q.append(root)
        result = []
        while q:
            levellist = deque()
            size = len(q)
            for _ in range(size):
                node = q.popleft()
                levellist.append(node.val)
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
	    #队列转化为列表
            result.append(list(levellist))
        return result

```
***

### **喜欢Programming-Cat的话，请Star吧**



