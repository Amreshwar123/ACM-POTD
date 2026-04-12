class Solution {
public:
    void dfs(vector<vector<int>>& image, int sr, int sc, int color, int newColor) {
        int n = image.size();
        int m = image[0].size();
        
        // Boundary + color check
        if (sr < 0 || sc < 0 || sr >= n || sc >= m || image[sr][sc] != color)
            return;
        
        image[sr][sc] = newColor;
        
        // 4 directions
        dfs(image, sr+1, sc, color, newColor);
        dfs(image, sr-1, sc, color, newColor);
        dfs(image, sr, sc+1, color, newColor);
        dfs(image, sr, sc-1, color, newColor);
    }
    
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int newColor) {
        int originalColor = image[sr][sc];
        
        // Important check to avoid infinite recursion
        if (originalColor == newColor)
            return image;
        
        dfs(image, sr, sc, originalColor, newColor);
        return image;
    }
};
