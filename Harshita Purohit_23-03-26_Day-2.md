# POTD DAY2

Name: Harshita Purohit
Date: 23-03-2026  
Platform: LeetCode  



## Problem Link
https://leetcode.com/problems/two-sum/description/



## Approach
Used hashmap to store values and indices
Checked for complement (target-num)
Achieved O(n) time complexity



## Code (C++)
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int,int>mp;
        
        for (int i=0; i<nums.size(); i++) {
            int complement=target-nums[i];
            
            if (mp.find(complement)!=mp.end()) {
                return {mp[complement],i};
            }
            
            mp[nums[i]]=i;
        }
        
        return {};    
    }
};


## Screenshot of Accepted Solution

<img width="1366" height="768" alt="Screenshot (702)" src="https://github.com/user-attachments/assets/3cc095d2-7029-43b8-ba51-d7a46f0b2c3a" />
