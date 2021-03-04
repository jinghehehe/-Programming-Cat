class Solution {
public:
    string replaceSpace(string s) {
        int pos;
        while((pos = s.find(" "))!=s.npos){
            s = s.replace(s.find(" "),1,"%20");
        }
        return s;
    }
};