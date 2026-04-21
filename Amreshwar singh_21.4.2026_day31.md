class Solution {
public:
    int climbStairs(int n) {
        // Base cases: if n is 1 or 2, there are 1 or 2 ways respectively.
        if (n <= 2) {
            return n;
        }

        int prev2 = 1; // Representing (n-2)
        int prev1 = 2; // Representing (n-1)
        int totalWays = 0;

        for (int i = 3; i <= n; i++) {
            totalWays = prev1 + prev2;
            // Shift our window: move prev2 to prev1's spot, and prev1 to the new total
            prev2 = prev1;
            prev1 = totalWays;
        }

        return prev1;
    }
};
