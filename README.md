# LeetCode Helper

A simple helper skill for solving LeetCode and coding interview problems using optimized C++ solutions.

## Features

- Optimized C++ solutions
- Beginner-friendly explanations
- Dry runs with examples
- Time and space complexity
- Line-by-line code explanation
- Common DSA patterns

## Supported Topics

- Arrays
- Strings
- Hash Maps
- Two Pointers
- Sliding Window
- Binary Search
- Stack / Queue
- Trees
- Graphs
- Dynamic Programming
- Greedy Algorithms
- Backtracking

## Example

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> seen;

        for (int i = 0; i < nums.size(); i++) {
            int need = target - nums[i];

            if (seen.count(need)) {
                return {seen[need], i};
            }

            seen[nums[i]] = i;
        }

        return {};
    }
};
```

## Usage

Paste any LeetCode problem and get:

1. Problem understanding
2. Optimized approach
3. Clean C++ code
4. Dry run
5. Complexity analysis
6. Edge cases

## Owner

Aniket Yadav

## License

MIT
