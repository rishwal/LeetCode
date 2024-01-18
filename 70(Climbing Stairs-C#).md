# 70. Climbing Stairs

## Problem Description

You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

### Example 1:

**Input:** `n = 2`  
**Output:** `2`  
**Explanation:** There are two ways to climb to the top:
1. 1 step + 1 step
2. 2 steps

### Example 2:

**Input:** `n = 3`  
**Output:** `3`  
**Explanation:** There are three ways to climb to the top:
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

## Solution

```csharp
public class Solution {
    public int ClimbStairs(int n) {
        if (n <= 2)
            return n;

        List<int> res = new List<int> { 1, 2 };

        for (int i = 2; i < n; i++)
        {
            res.Add(res[i - 1] + res[i - 2]);
        }
        return res[res.Count - 1];
    }
}
```

## Explanation

The problem is solved using dynamic programming. The `res` list stores the number of distinct ways to climb to each step. The loop calculates the distinct ways iteratively based on the previous steps.

## Time Complexity

The time complexity is O(n) because we iterate through all steps once.

## Space Complexity

The space complexity is O(n) due to the space used by the `res` list.
