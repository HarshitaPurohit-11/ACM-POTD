POTD DAY 22
Date: 12-04-2026

Question:
Flood Fill

Solution:
class Solution {
public:
    void dfs(vector<vector<int>>& image, int r, int c, int oldColor, int newColor) {
        int m = image.size();
        int n = image[0].size();

        if (r < 0 || r >= m || c < 0 || c >= n || image[r][c] != oldColor)
            return;

        image[r][c] = newColor;

        dfs(image, r + 1, c, oldColor, newColor);
        dfs(image, r - 1, c, oldColor, newColor);
        dfs(image, r, c + 1, oldColor, newColor);
        dfs(image, r, c - 1, oldColor, newColor);
    }

    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int color) {
        int oldColor = image[sr][sc];

        if (oldColor == color) return image;

        dfs(image, sr, sc, oldColor, color);
        return image;
    }
};

Algorithm:
Store original color
If same as new color → return
Use DFS to visit all 4-directionally connected pixels
Replace color while traversing

Complexity:
Time: O(m × n)
Space: O(m × n) (recursion stack)

Screenshots:
<img width="1366" height="768" alt="Screenshot (971)" src="https://github.com/user-attachments/assets/eda8ce3c-4dd0-43ce-969d-171904348f42" />
<img width="1366" height="768" alt="Screenshot (970)" src="https://github.com/user-attachments/assets/5364e351-9de7-4ad4-af65-4f4233d0abe6" />

