POTD DAY-4
Missing Numbers

Solution:
If we know the expected sum of numbers from 0 to n, and subtract the actual sum of the array, the result will be the missing number.

Steps:
Compute n=size of array
Calculate expected sum using formula
Traverse the array and compute actual sum
Return expected_sum-actual_sum

Time complexity:
o(n)

Code:

class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n=nums.size();
        
        long long expected=(long long)n*(n+1)/2;
        long long actual=0;
        
        for (int i=0;i<n;i++){
            actual+=nums[i];
        }
        
        return (int)(expected-actual);
        
    }
};

Screenshot:
<img width="1366" height="768" alt="Screenshot (718)" src="https://github.com/user-attachments/assets/20246f50-e7f3-4b43-924b-fbc20452f08b" />
