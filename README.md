# DAA - Dynamic Programming (C Implementations)

This repository contains C implementations of classic **Dynamic Programming (DP)** problems commonly studied in **Design and Analysis of Algorithms (DAA)**.

## 📌 Problem Overview

| # | File Name | Problem Name | DP Strategy / Recurrence | Time Complexity | Space Complexity |
|---|---|---|---|---|---|
| 1 | `1-DP-Playing with Numbers` | Playing with Numbers (Ways to Reach N) | $dp[i] = dp[i-1] + dp[i-3]$ with steps of size 1 and 3 | $\mathcal{O}(N)$ | $\mathcal{O}(N)$ |
| 2 | `2-DP-Playing with chessboard` | Playing with Chessboard (Max Path Sum) | $dp[i][j] = a[i][j] + \max(dp[i-1][j], dp[i][j-1])$ | $\mathcal{O}(N^2)$ | $\mathcal{O}(N^2)$ |
| 3 | `3-DP-Longest Common Subsequence` | Longest Common Subsequence (LCS) | Match: $1 + dp[i-1][j-1]$; Mismatch: $\max(dp[i-1][j], dp[i][j-1])$ | $\mathcal{O}(M \times N)$ | $\mathcal{O}(M \times N)$ |
| 4 | `4-DP-Longest non-decreasing Subsequence` | Longest Non-Decreasing Subsequence | For $j < i$ and $a[j] \le a[i]$: $dp[i] = \max(dp[i], dp[j] + 1)$ | $\mathcal{O}(N^2)$ | $\mathcal{O}(N)$ |

---

## 📖 Problem Details

### 1. Playing with Numbers (`1-DP-Playing with Numbers`)
- **Objective:** Calculate the total number of ways to form or reach a number $n$ using combinations of step sizes (specifically steps of $1$ and $3$).
- **Base Case:** $dp[0] = 1$
- **Recurrence Relation:**
  $$dp[i] = dp[i-1] + (i \ge 3 \text{ ? } dp[i-3] : 0)$$

### 2. Playing with Chessboard (`2-DP-Playing with chessboard`)
- **Objective:** Find the maximum score / sum collected while traversing an $n \times n$ chessboard grid from the top-left cell $(0,0)$ to the bottom-right cell $(n-1, n-1)$.
- **Allowed Moves:** Right $(\to)$ and Down $(\downarrow)$.
- **Recurrence Relation:**
  $$dp[i][j] = a[i][j] + \max(dp[i-1][j], dp[i][j-1])$$

### 3. Longest Common Subsequence (`3-DP-Longest Common Subsequence`)
- **Objective:** Find the length of the longest subsequence present in both given strings $s_1$ (length $m$) and $s_2$ (length $n$).
- **Recurrence Relation:**
  - If $s_1[i-1] == s_2[j-1]$:
    $$dp[i][j] = dp[i-1][j-1] + 1$$
  - Otherwise:
    $$dp[i][j] = \max(dp[i-1][j], dp[i][j-1])$$

### 4. Longest Non-Decreasing Subsequence (`4-DP-Longest non-decreasing Subsequence`)
- **Objective:** Determine the length of the longest subsequence of array $a$ such that each element is greater than or equal to the preceding element ($a[j] \le a[i]$).
- **Recurrence Relation:**
  $$dp[i] = 1 + \max(\{dp[j] \mid 0 \le j < i \text{ and } a[j] \le a[i]\} \cup \{0\})$$

---

## 🚀 How to Run

Compile and run any solution using GCC (or Clang):

```bash
# Example: Compile Longest Common Subsequence
gcc "3-DP-Longest Common Subsequence" -o lcs

# Run executable
./lcs
```

---

## 👤 Author
- **Sanjay R** ([@Sanjay-AI-ML](https://github.com/Sanjay-AI-ML))
