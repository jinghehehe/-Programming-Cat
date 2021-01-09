# 剑指 Offer 04. 二维数组中的查找
***
来源： LeetCode 热题Hot-100
相关企业： 亚马逊， 字节跳动， 微软
相关标签： 树， 广度优先搜索
难度： 中等
相似题目：  二叉树的锯齿形层序遍历(同类型题)，二叉树的层序遍历 II
***
## 题干内容
给你一个二叉树，请你返回其按 层序遍历 得到的节点值。 （即逐层地，从左到右访问所有节点）

示例：
二叉树：[3,9,20,null,null,15,7],

![](https://github.com/jinghehehe/pictures/blob/main/103-1.png)

返回其层序遍历结果：

![](https://github.com/jinghehehe/pictures/blob/main/102-2.png)

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/binary-tree-level-order-traversal/
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## 题眼题解
### 题眼:
**本题是针对树的广度优先搜索进行考察，重点牢记广度优先搜索模板**

- 首先树根节点判空，然后队列添加根节点，队列不为空时，依次取出队首元素，将其放入题干所需数组中，并将队首元素的子节点添加到队列尾部，每一层元素均被放在一个数组中，即广度优先搜索思想。


### 题解：
#### c++版本一，时间复杂度 O(n), 空间复杂度 O(n)。
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



