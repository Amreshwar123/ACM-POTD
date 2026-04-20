class Solution {
public:
    bool isPowerOfTwo(int n) {
      
      


        // A power of two must be positive.
        // The expression (n & (n - 1)) clears the least significant bit.
        // For a power of two, there is only one bit set, so clearing it results in 0.
        return n > 0 && (n & (n - 1)) == 0;
    }
}; 
