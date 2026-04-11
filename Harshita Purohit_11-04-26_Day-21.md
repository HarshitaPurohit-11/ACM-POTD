POTD Day 21
Date: 11-04-2026

QUESTION:
Make The String Great

ALGORITHM:
1. Initialize an empty string result (acts like a stack).
2. Traverse each character c in the given string s:
        If result is not empty AND
       the last character of result and c are the same letter but different case
        (i.e., abs(result.back() - c) == 32):
                Remove the last character from result (pop).
        Else:
                 Add c to result (push).
3. Repeat until all characters are processed.
4. Return result as the final good string.

COMPLEXITY:
Time: O(n)
Space: O(n)

SOLUTION:
class Solution {
public:
    string makeGood(string s) {
        string result;

        for (char c:s) {
            if (!result.empty() && abs(result.back() - c)==32){
                result.pop_back();
            }else{
                result.push_back(c);
            }
        }

        return result;
        
    }
};

SCREENSHOT:
<img width="1366" height="768" alt="Screenshot (967)" src="https://github.com/user-attachments/assets/61a600a3-7f5d-43a2-8653-7d4cf2b94f2f" />
