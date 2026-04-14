POTD DAY 24
Date: 14-04-2026

Question:
Find Center of Star Graph

Solution:
class Solution {
public:
    int findCenter(vector<vector<int>>& edges) {
        if (edges[0][0]==edges[1][0] || edges[0][0]==edges[1][1])
            return edges[0][0];
        else
            return edges[0][1];  
    }
};

Algorithm:
1. Take the first two edges:
      edges[0] = [a, b]
      edges[1] = [c, d]
2. Compare nodes:
      If a is equal to c or d, then a is the center.
       Otherwise, b is the center.

Complexity:
Time: O(1) (only checking first two edges)
Space: O(1)


Screenshot:
<img width="1366" height="768" alt="Screenshot (1055)" src="https://github.com/user-attachments/assets/97d6bb55-809f-4b69-9595-b0e466ff9036" />
