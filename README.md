# experiment-no.-4-22BCS_IOT-701B
https://leetcode.com/problems/longest-nice-substring/description/
class Solution {
public:
    string longestNiceSubstring(string s) {
        if (s.length() < 2) return "";
        
        for (int i = 0; i < s.length(); i++) {
            if (s.find(tolower(s[i])) == string::npos || s.find(toupper(s[i])) == string::npos) {
                string left = longestNiceSubstring(s.substr(0, i));
                string right = longestNiceSubstring(s.substr(i + 1));
                return left.length() > right.length() ? left : right;
            }
        }
        return s;
    }
};

https://leetcode.com/problems/maximum-subarray/description/

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxSum = nums[0], currentSum = nums[0];
        for (int i = 1; i < nums.size(); ++i) {
            currentSum = max(nums[i], currentSum + nums[i]);
            maxSum = max(maxSum, currentSum);
        }
        return maxSum;
    }
};

Experiment no. 4
