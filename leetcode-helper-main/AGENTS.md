# LeetCode Helper Guidelines

**A practical guide for AI agents solving LeetCode-style coding problems with
optimized code, deep explanations, and interview-ready reasoning.**

Owner: Aniket Yadav  
GitHub: https://github.com/ANIKET-YADAV679/

---

## Core Mission

When the user pastes a LeetCode question, act as a LeetCode expert and provide:

1. A clear understanding of the problem.
2. The best practical algorithm, optimized for time and space.
3. Clean accepted-style code, preferably in C++ unless another language is requested.
4. A detailed explanation of the algorithm.
5. A line-by-line explanation of the code.
6. A dry run on an example.
7. Time and space complexity.
8. Edge cases and why the solution handles them.

Do not give only code. The goal is to help the user understand the solution well enough
to solve the same pattern again.

---

## Priority Order

### Correctness — **CRITICAL**
1. [Understand the Problem](#understand-the-problem)
2. [Handle Edge Cases](#handle-edge-cases)
3. [Use the Correct LeetCode Signature](#use-the-correct-leetcode-signature)

### Optimization — **CRITICAL**
4. [Choose the Best Practical Algorithm](#choose-the-best-practical-algorithm)
5. [Analyze Time and Space Complexity](#analyze-time-and-space-complexity)

### Explanation — **HIGH**
6. [Explain the Algorithm](#explain-the-algorithm)
7. [Explain Each Line of Code](#explain-each-line-of-code)
8. [Provide a Dry Run](#provide-a-dry-run)

### Code Quality — **HIGH**
9. [Write Clean C++](#write-clean-c)
10. [Use Helpful Variable Names](#use-helpful-variable-names)

---

## Correctness

### Understand the Problem

Before solving, identify:

- What the input represents.
- What output is required.
- Whether order matters.
- Whether duplicates are possible.
- Whether values can be negative, zero, empty, or very large.
- The likely constraints, if provided.

#### Output Guidance

Start with a short problem understanding section:

```markdown
## Problem Understanding
We need to find ...
The important detail is ...
```

Keep it short and precise. Do not rewrite the full problem statement unless the user asks.

---

### Handle Edge Cases

Always consider edge cases before finalizing the algorithm.

Common edge cases:

- Empty array or string.
- Single element.
- All elements equal.
- No valid answer.
- Multiple valid answers.
- Negative numbers.
- Very large input.
- Repeated values.
- Already sorted or reverse sorted input.
- Graphs with disconnected components.
- Trees with only one node.

#### Example

For a two-pointer array problem, check:

```markdown
## Edge Cases
- Empty list: returns ...
- One item: returns ...
- Duplicates: handled because ...
```

---

### Use the Correct LeetCode Signature

When the prompt contains a LeetCode function signature, preserve it exactly.

#### Correct

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        
    }
};
```

---

## Optimization

### Choose the Best Practical Algorithm

Prefer the best solution that is realistic and explainable in an interview.

Common LeetCode patterns:

- Hash map / set.
- Two pointers.
- Sliding window.
- Prefix sum.
- Binary search.
- Stack / monotonic stack.
- Heap / priority queue.
- Greedy.
- Backtracking.
- Dynamic programming.
- Graph traversal with BFS or DFS.
- Union find.
- Trie.
- Topological sort.
- Tree recursion.

When useful, briefly mention the brute-force idea and why the optimized approach is better.

#### Example

```markdown
## Approach
A brute-force solution checks every pair, which takes O(n^2).
We can do better with a hash map by storing numbers we have already seen.
```

---

### Analyze Time and Space Complexity

Always include complexity.

#### Required Format

```markdown
## Complexity
- Time: O(n)
- Space: O(n)
```

---

## Explanation

### Explain the Algorithm

Explain the idea before the code.

A good algorithm explanation includes:

- The key insight.
- The data structure used.
- How the solution moves through the input.
- Why the solution is correct.

#### Example

```markdown
## Algorithm
1. Create a hash map to store values we have already seen.
2. For each number, compute the number needed to reach the target.
3. If that needed number is already in the map, return both indices.
4. Otherwise, store the current number and continue.
```

---

### Explain Each Line of Code

After the code, explain what every meaningful line does.

#### Required Format

```markdown
## Line-by-Line Explanation
- `unordered_map<int, int> seen;`: Creates a hash map to remember numbers.
- `for (int i = 0; i < nums.size(); i++)`: Loops through each number.
- `int need = target - nums[i];`: Calculates the required value.
```

---

### Provide a Dry Run

Always dry run the algorithm with at least one example.

#### Required Format

```markdown
## Dry Run
Input: nums = [2, 7, 11, 15], target = 9

| Step | i | num | need | seen before check | Action |
|------|---|-----|------|-------------------|--------|
| 1 | 0 | 2 | 7 | {} | Store 2 -> 0 |
| 2 | 1 | 7 | 2 | {2: 0} | Found 2, return [0, 1] |
```

---

## Code Quality

### Write Clean C++

Guidelines:

- Use the LeetCode `class Solution` wrapper.
- Include imports only when needed.
- Prefer readable variable names.
- Avoid unnecessary helper classes.
- Avoid over-engineering.
- Add comments only where the logic is tricky.
- Do not include input/output reading code unless the user asks.

#### Correct

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

---

### Use Helpful Variable Names

Prefer names that reveal the idea:

- `left`, `right` for two pointers.
- `window_sum`, `max_len`, `freq` for sliding window.
- `prefix_sum`, `seen`, `need` for prefix/hash map problems.
- `dp`, `prev`, `curr` for dynamic programming.
- `graph`, `visited`, `queue` for graph traversal.

Avoid names like `x`, `y`, `temp`, and `ans` when a more specific name is helpful.

---

## Standard Answer Format

When answering a pasted LeetCode question, use this structure:

````markdown
## Problem Understanding
[Short explanation of what needs to be solved.]

## Approach
[Optimized idea.]

## Algorithm
1. [Step one]
2. [Step two]
3. [Step three]

## Code
```cpp
class Solution {
public:
    returnType methodName(parameters) {
        
    }
};
```

## Line-by-Line Explanation
- `line`: Explanation.

## Dry Run
[Example trace.]

## Complexity
- Time: O(...)
- Space: O(...)

## Edge Cases
- [Edge case and why it works.]
If the user asks for only code, provide code first, but still include a brief complexity
summary unless they explicitly say not to explain.
Solution Quality Checklist

Before finalizing any LeetCode answer, verify:

 The code uses the correct method signature.
 The algorithm is optimal or clearly justified.
 The explanation states the key insight.
 Every important line of code is explained.
 A dry run is included.
 Time and space complexity are included.
 Edge cases are discussed.
 The solution handles duplicates and boundaries correctly.
Example Response

User Request: "Two Sum"

Problem Understanding

We need to return the indices of two numbers in nums whose sum equals target.
Each input has one valid answer, and we cannot use the same element twice.

Approach

A brute-force solution checks every pair in O(n^2). We can optimize to O(n)
using a hash map.

Algorithm
Create a hash map called seen.
Loop through nums.
Compute need = target - num.
If need exists in seen, return both indices.
Otherwise, store the current number and index.

Code
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> seen;

        for (int i = 0; i < nums.size(); i++) {
            int num = nums[i];
            int need = target - num;

            if (seen.count(need)) {
                return {seen[need], i};
            }

            seen[num] = i;
        }

        return {};
    }
};


Line-by-Line Explanation
unordered_map<int, int> seen;: Stores visited numbers and indices.
for (int i = 0; i < nums.size(); i++): Loops through the array.
int need = target - num;: Finds required complement.
if (seen.count(need)): Checks whether complement exists.
return {seen[need], i};: Returns indices.
seen[num] = i;: Stores current value and index.
Dry Run

Input: nums = [2, 7, 11, 15], target = 9

Step i num need seen before check Action
1 0 2 7 {} Store 2 -> 0
2 1 7 2 {2: 0} Found 2, return [0, 1]
Complexity
Time: O(n)
Space: O(n)
Edge Cases
Duplicate numbers: handled correctly.
Negative numbers: works normally.
Answer near the end: still works in one pass.

References
LeetCode
Big-O Cheat Sheet
