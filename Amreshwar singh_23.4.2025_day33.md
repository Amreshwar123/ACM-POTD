#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n = cost.size();
        
        // Starting values: cost to be at step 0 and step 1
        int prev2 = cost[0];
        int prev1 = cost[1];
        
        // Start from the third step (index 2)
        for (int i = 2; i < n; ++i) {
            // The cost to reach current step is its cost + the minimum of the two before it
            int current = cost[i] + min(prev1, prev2);
            
            // Shift our window forward
            prev2 = prev1;
            prev1 = current;
        }
        
        // The goal is to reach the floor 'beyond' the last index.
        // We can get there from either the last or second-to-last step.
        return min(prev1, prev2);
    }
};
