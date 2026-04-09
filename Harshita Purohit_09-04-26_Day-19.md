POTD DAY 19
Date: 09-04-2026

Question:
Backspace String Compare

Algorithm:
1. Start from the end of both strings using two pointers.
2. Use counters to track how many characters to skip due to #.
3. Move backwards:
    If # → increase skip count
    If skip > 0 → skip character
4. Compare the next valid characters of both strings.
5. If mismatch → return false.
6. If all match → return true.

Solution:
class Solution {
public:
    bool backspaceCompare(string s, string t) {
        int i=s.length()-1;
        int j = t.length()-1;

        int skipS=0,skipT=0;

        while (i>=0||j>=0) {
            while (i>= 0) {
                if (s[i] == '#') {
                    skipS++;
                    i--;
                } else if (skipS> 0) {
                    skipS--;
                    i--;
                } else {
                    break;
                }
            }

            while (j>= 0) {
                if (t[j]== '#') {
                    skipT++;
                    j--;
                } else if (skipT > 0) {
                    skipT--;
                    j--;
                } else {
                    break;
                }
            }

            if (i>=0 && j>=0) {
                if (s[i] != t[j]) return false;
            } else {
                if (i>=0 || j>=0) return false;
            }

            i--;
            j--;
        }

        return true;
    }
        
};

Complexity
Time: O(n)
Space: O(1)

Screenshots:

<img width="1366" height="768" alt="Screenshot (962)" src="https://github.com/user-attachments/assets/10e9b988-015d-4a0b-b35e-3e39c68537d8" />
<img width="1366" height="768" alt="Screenshot (961)" src="https://github.com/user-attachments/assets/36a3ba97-65fa-46b7-b2fc-01da5485aa7d" />
<img width="1366" height="768" alt="Screenshot (960)" src="https://github.com/user-attachments/assets/23f1f8ca-6b63-4a2a-885b-3966170879f1" />
<img width="1366" height="768" alt="Screenshot (959)" src="https://github.com/user-attachments/assets/e83f36b7-8ab0-4a28-aa7c-4547b8cad1bb" />
