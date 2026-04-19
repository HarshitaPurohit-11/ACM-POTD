POTD DAY 29
DATE : 19-04-2026

QUESTION:
Fibonacci Number

SOLUTION:
class Solution {
public:
    int fib(int n) {
        if (n<=1) return n;
        
        int prev2 = 0; 
        int prev1 = 1;
        
        for (int i = 2; i <= n; i++) {
            int curr=prev1 + prev2;
            prev2=prev1;
            prev1=curr;
        }
        
        return prev1;
    }
};

ALGORITHM:

1. If n <= 1, return n
2. Initialize:
      prev2=0
      prev1=1
3. Loop from i=2 to n:
      curr=prev1+prev2
      prev2=prev1
      prev1=curr
4. Return prev1

COMPLEXITY:
Time Complexity: O(n)
Space Complexity: O(1) (no extra space used)

SCREENSHOT:
<img width="1366" height="768" alt="Screenshot (1177)" src="https://github.com/user-attachments/assets/7797e4e7-6fa0-4ba1-8266-f342a505b65e" />
