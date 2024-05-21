# Problem 78: Subsets

## Problem Statement
Given an integer array `nums` of unique elements, return all possible subsets (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

### Example 1

Input:
```
nums = [1,2,3]
```
Output:
```
[[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
```

### Example 2

Input:
```
nums = [0]
```
Output:
```
[[],[0]]
```

### Constraints
- `1 <= nums.length <= 10`
- `-10 <= nums[i] <= 10`
- All the numbers of `nums` are unique.

## Solution

### Approach
To generate all possible subsets of the array, we can use the concept of bit manipulation. Each subset can be represented by a binary number where each bit represents whether the corresponding element is included in the subset or not.

### Detailed Steps
1. Calculate the length of the input array `nums`.
2. Compute the total number of subsets, which is `2^n` where `n` is the length of the array.
3. Iterate through each number from `0` to `2^n - 1` and for each number, create a subset by checking each bit position.
4. If a bit is set (i.e., `1`), include the corresponding element from `nums` in the subset.
5. Add the generated subset to the result list.
6. Return the list of all subsets.

### Code

```csharp
public class Solution 
{
    public IList<IList<int>> GenerateSubset(int[] nums)
    {
        IList<IList<int>> list = new List<IList<int>>();
        int len = nums.Length;
        int pLen = 1 << len;

        for (int i = 0; i < pLen; i++)
        {
            IList<int> subset = new List<int>();
            for (int j = 0; j < len; j++)
            {
                if ((i & (1 << j)) > 0)
                {
                    subset.Add(nums[j]);
                }
            }
            list.Add(subset);
        }
        return list;
    }

    public IList<IList<int>> Subsets(int[] nums) 
    {
        return GenerateSubset(nums);
    }
}
```

### Complexity Analysis

#### Time Complexity
- The time complexity is \(O(2^n \cdot n)\), where \(n\) is the length of the input array. This is because there are \(2^n\) subsets and generating each subset takes \(O(n)\) time.

#### Space Complexity
- The space complexity is \(O(2^n \cdot n)\) to store all the subsets. There are \(2^n\) subsets and each subset can contain at most \(n\) elements.
```
