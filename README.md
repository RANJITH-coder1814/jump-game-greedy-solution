# Jump Game (LeetCode 55)

## Problem
Given an array where each element represents the maximum jump length,
determine if you can reach the last index.

## Approach
We use a greedy strategy:
- Track the farthest reachable index (`maxReach`)
- If current index exceeds `maxReach`, return false
- Update `maxReach` at each step

## Code
```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int maxReach = 0;

        for (int i = 0; i < nums.size(); i++) {
            if (i > maxReach) return false;
            maxReach = max(maxReach, i + nums[i]);
        }
        return true;
    }
};
