POTD DAY 30
DATE: 21-04-2026

QUESTION:
Power of Two

SOLUTIION:
class Solution {
public:
    bool isPowerOfTwo(int n) {
    return n>0 && (n&(n-1))==0;
    }
};

ALGORITHM:
1. If n<=0, return false
2. Check (n&(n-1))
3. If result is 0, return true (power of 2)
4. Else return false


COMPLEXITY:
Time: O(1)
Space: O(1)

SCREENSHOT:
<img width="1366" height="706" alt="Screenshot (1206)" src="https://github.com/user-attachments/assets/2076bcde-5199-4813-88c2-b6f450d33e45" />



