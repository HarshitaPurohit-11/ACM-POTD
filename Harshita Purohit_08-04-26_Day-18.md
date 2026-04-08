POTD DAY 18
Date: 08-04-2026

Question:
Remove All Adjacent Duplicates In String

Algorithm:
1. Initialize an empty string result (acts like a stack).
2. Traverse each character c in s:
        If result is not empty and last character == c, remove last character.
        Else, add c to result.
3. Return result.


Complexity:
Time: O(n)
Space: O(n) (in worst case)

Solution:
class Solution {
public:
    string removeDuplicates(string s) {
        string result=""; 
        
        for (char c : s) {
            if (!result.empty() && result.back()==c) {
                result.pop_back();
            }else{
                result.push_back(c);
            }
        }
        
        return result;
        
    }
};

Screenshot:
<img width="1366" height="768" alt="Screenshot (947)" src="https://github.com/user-attachments/assets/b4a924d9-6c55-42c7-b797-df631e266208" />
