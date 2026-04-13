POTD DAY 23
Find the Town Judge

Date: 13-04-2026

Question:
Find the Town Judge

Solution:
class Solution {
public:
    int findJudge(int n, vector<vector<int>>& trust) {
        vector<int> score(n+1,0);

        for (auto &t:trust) {
            int a=t[0];
            int b=t[1];
            score[a]--;
            score[b]++;
        }

        for (int i=1; i<=n; i++) {
            if (score[i] == n-1) {
                return i;
            }
        }

        return -1;
    }
};


Algorithm:

1. Create an array score of size n + 1 initialized to 0.
2. For each trust pair [a, b]:
        Decrease score[a] (since a trusts someone)
        Increase score[b] (since b is trusted)
3. Traverse from 1 to n:
        If score[i] == n - 1, return i (judge found)
4. If no such person exists, return -1.


Complexity:
Time Complexity: O(n+t) (where t=trust.size())
Space Complexity: O(n)

Screenshots:

<img width="1366" height="768" alt="Screenshot (1021)" src="https://github.com/user-attachments/assets/58bb4525-6dc0-4bad-adec-755a77a5fc83" />
<img width="1366" height="768" alt="Screenshot (1020)" src="https://github.com/user-attachments/assets/9ea5e6b9-70a2-4644-a257-2279b1edb046" />
