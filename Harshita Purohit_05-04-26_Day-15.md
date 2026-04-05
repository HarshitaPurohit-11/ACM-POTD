POTD DAY 15
Date: 05-04-2026

Question:
Valid Parentheses


Algorithm:
Input: A string s containing only ()[]{}.
Output: true if the brackets are valid, false otherwise.

1. Initialize an empty stack st.
2. Iterate over each character c in the string s:
        If c is an opening bracket ((, {, [), push it onto the stack.
        Else (it is a closing bracket):
              If the stack is empty, return false (no matching opening bracket).
              If the top of the stack does not match the corresponding opening bracket for c, return false.
             Otherwise, pop the top of the stack.
3. After finishing the loop, check the stack:
        If the stack is empty, all brackets matched → return true.
        If the stack is not empty, there are unmatched opening brackets → return false.


Time Complexity:
Each character in the string is processed exactly once.
Stack operations (push and pop) are O(1).
Time Complexity=O(n)

Where n is the length of the string s.

Space Complexity:
In the worst case, all characters are opening brackets, so the stack stores all n characters.
Space Complexity=O(n)


Solution:

class Solution {
public:
    bool isValid(string s) {
        stack<char> st;

        for (char c : s) {
            if (c == '(' || c == '{' || c == '[') {
                st.push(c);
            } else {
                if (st.empty()) return false;

                if (c == ')' && st.top() != '(') return false;
                if (c == '}' && st.top() != '{') return false;
                if (c == ']' && st.top() != '[') return false;

                st.pop();
            }
        }

        return st.empty();
    }
};

Screenshot:

<img width="1366" height="768" alt="Screenshot (867)" src="https://github.com/user-attachments/assets/0597a1ae-14bf-442b-8848-eecb032061d9" />
