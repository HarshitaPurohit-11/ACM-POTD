POTD DAY 20
Date: 10-04-2026

Question:
Remove Outermost Parentheses

Algorithm:
1. Initialize
      Create an empty string result.
      Set an integer depth = 0.
2. Traverse the string
      For each character c in string s:
        If c == '(':

              If depth > 0, append '(' to result.
             Increment depth by 1.

        If c == ')':

              Decrement depth by 1.
               If depth > 0, append ')' to result.
3. Return result
      After processing all characters, return result.

Complexity:
Time: O(n)
Space: O(n)

Solution:

class Solution {
public:
    string removeOuterParentheses(string s) {
        string result="";
        int depth=0;

        for (char c:s) {
            if (c=='(') {
                if (depth > 0) {
                    result += c;
                }
                depth++;
            } else {
                depth--;
                if (depth> 0) {
                    result+= c;
                }
            }
        }

        return result;
        
    }
};

Screenshots:

<img width="1366" height="768" alt="Screenshot (964)" src="https://github.com/user-attachments/assets/8821b9a7-9177-431f-b298-f5e88f4a25ac" />
<img width="1366" height="768" alt="Screenshot (963)" src="https://github.com/user-attachments/assets/c9f6cbfa-1910-461f-b8d3-d96ccccf478e" />

   
