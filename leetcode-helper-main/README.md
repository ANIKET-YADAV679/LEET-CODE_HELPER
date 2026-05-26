# LeetCode Helper

LeetCode Helper is a Codex skill for solving LeetCode-style coding interview
problems with optimized solutions and detailed explanations.

## Owner
Aniket Yadav 
GitHub: https://github.com/ANIKET-YADAV679/

## What It Does

When you paste a LeetCode problem, this skill guides the agent to provide:

- Problem understanding in plain language.
- An optimized algorithmic approach.
- Clean LeetCode-ready C++ code.
- Step-by-step algorithm explanation.
- Line-by-line code explanation.
- A dry run using an example.
- Time and space complexity.
- Important edge cases.

## Skill Files

- `SKILL.md`: Skill metadata and high-level instructions.
- `AGENTS.md`: Detailed behavior rules, answer format, and examples.

## Example Use

Paste a LeetCode question and ask for an optimized solution. The response should
include the algorithm, code, explanation, dry run, complexity analysis, and edge
cases.

## Example C++ Solution

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

## Features

- Optimized algorithms.
- Interview-ready explanations.
- Clean and readable C++ code.
- Dry runs and edge-case analysis.
- Time and space complexity discussion.
- Pattern recognition for coding interviews.

## Supported Algorithm Patterns

- Hash Map / Set
- Two Pointers
- Sliding Window
- Prefix Sum
- Binary Search
- Stack / Monotonic Stack
- Heap / Priority Queue
- Greedy
- Backtracking
- Dynamic Programming
- BFS / DFS
- Union Find
- Trie
- Topological Sort
- Tree Recursion

## License

MIT