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
<img width="1366" height="706" alt="Screenshot (1205)" src="https://github.com/user-attachments/assets/6671ce96-3c0b-4b82-9cf6-4d3e419c037f" />

