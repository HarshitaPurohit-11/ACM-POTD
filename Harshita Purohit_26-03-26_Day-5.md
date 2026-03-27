POTD DAY 5

*Question:
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.
Note that you must do this in-place without making a copy of the array.

*Approach:

Used a two pointer technique:

Maintain a pointer (insertPos) to track where the next non zero element should be placed.
Traverse the array:
If the current element is non zero, place it at insertPos and move the pointer forward.
After placing all non zero elements, fill the remaining positions with 0.

*Code:

class Solution {
public:
    void moveZeroes(vector<int>&nums){
        int insertPos=0;
        for (int k=0;k<nums.size();k++){
            if (nums[k]!=0){
                nums[insertPos++]=nums[k];
            }
        }

        for (int k=insertPos; k<nums.size(); k++){
            nums[k]=0;
        }    
    }
};

Screenshot:



<img width="1366" height="768" alt="Screenshot (726)" src="https://github.com/user-attachments/assets/5ecf1049-7ff6-4fab-b578-ce3cfb5beef0" />
