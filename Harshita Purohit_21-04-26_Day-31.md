POTD DAY 31
DATE: 21-04-2026

QUESTION:
Climbing Stairs

SOLUTION:
class Solution {
public:
    int climbStairs(int n) {
        if (n<=2) return n;

        int prev1=1, prev2=2, curr;

        for (int i=3; i<=n; i++) {
            curr=prev1+prev2;
            prev1=prev2;
            prev2=curr;
        }
        return prev2;
    }
};

ALGORITHM:
1. If n<=2, return n
2. Initialize a=1,b=2
3. For i=3 to n:
      c=a+b
      a=b
      b=c
4. Return b

COMPLEXITY:
Time: O(n)
Space: O(1)

SCREENSHOT:
<img width="1366" height="711" alt="Screenshot (1207)" src="https://github.com/user-attachments/assets/8ff2d9fc-24bd-4c32-a614-3dc32b6f750c" />

