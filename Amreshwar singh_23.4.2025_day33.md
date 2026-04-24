#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n = cost.size();
        
        
        int prev2 = cost[0];
        int prev1 = cost[1];
        
        
        for (int i = 2; i < n; ++i) {
            // The cost to reach current step is its cost + the minimum of the two before it
            int current = cost[i] + min(class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n = cost.size();
        
        int prev2 = cost[0];  // dp[i-2]
        int prev1 = cost[1];  // dp[i-1]

        for (int i = 2; i < n; i++) {
            int curr = cost[i] + min(prev1, prev2);
            prev2 = prev1;
            prev1 = curr;
        }

        return min(prev1, prev2);
    }
};
            
           
            
