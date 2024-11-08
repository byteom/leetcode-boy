# Competitive Programming Solutions

This repository contains solutions to various coding problems with detailed explanations. Each solution is implemented in C++ and includes an explanation to help understand the approach and complexity analysis.

---

## Table of Contents
- [2275. Largest Combination With Bitwise AND Greater Than Zero](#2275-largest-combination-with-bitwise-and-greater-than-zero)
- [Future Problems](#future-problems)

---

### 2275. Largest Combination With Bitwise AND Greater Than Zero

**Problem Statement**: Given a list of integers, find the largest subset where the bitwise AND of all elements is greater than zero. 

### Solution Explanation

```cpp
class Solution {
 public:
  int largestCombination(vector<int>& candidates) {
    constexpr int kMaxBit = 24;
    int ans = 0;

    for (int i = 0; i < kMaxBit; ++i) {
      int count = 0;
      for (const int candidate : candidates)
        if (candidate >> i & 1)
          ++count;
      ans = max(ans, count);
    }

    return ans;
  }
};
