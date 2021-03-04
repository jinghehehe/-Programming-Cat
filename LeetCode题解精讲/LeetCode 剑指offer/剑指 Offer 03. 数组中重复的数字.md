解法一
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        int len = nums.size();
        unordered_map<int,int> mp;
        for(int i=0;i<len;i++){
            if(mp.find(nums[i])!=mp.end()){
                return nums[i];
            }
            mp[nums[i]]++;
        }
        return -1;
    }
};
解法二
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        int len = nums.size();
        for(int i=0;i<len;i++){
            while(i!=nums[i]){
                if(nums[i] == nums[nums[i]]){
                    return nums[i];
                }
                swap(nums[i],nums[nums[i]]);
            }
        }
        return -1;
    }
};