---
title: "Microsoft Interview Experience"
mathjax: true
layout: post
---

I recently had the opportunity to interview with **Microsoft** for an **SDE-2 position** on the **Ads team**. Below, I’ll walk through the problems I was given and how I approached them.

*Note: The problems described here are reconstructed from memory for educational purposes and may not reflect the exact wording used during the interview.*

---

## Round 1: Shipping Packages Within Days

### Problem Statement

You are given an array `weights` where `weights[i]` represents the weight of the `i`‑th package. The task is to ship these packages within `days` days. Each day, you can ship a continuous subarray of packages, but the total weight on that day must not exceed a given capacity.

The goal is to find the **minimum capacity of a ship** that allows all packages to be shipped within `days`.

### Example

#### Input:
```
weights = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
days = 5;
```

#### Output:
```
15
```

### Explanation

A valid way to ship the packages in **5 days** with a ship of capacity **15** is:

- **Day 1**: `[1, 2, 3, 4, 5]` (Total = 15)  
- **Day 2**: `[6, 7]` (Total = 13)  
- **Day 3**: `[8]` (Total = 8)  
- **Day 4**: `[9]` (Total = 9)  
- **Day 5**: `[10]` (Total = 10)

### Approach

This is a classic **binary search on answer** problem:

- **Lower bound**: The heaviest package.
- **Upper bound**: The sum of all package weights.
- Perform binary search to find the minimum capacity that allows shipping within the given number of days.

---

## Round 2: Removing K Digits to Form the Smallest Number

### Problem Statement

Given a number `n` (as a string) and an integer `k`, remove `k` digits from `n` to form the **smallest possible number** while preserving the **relative order of the digits**.

### Example 1

#### Input:
```
n = 1432219, k = 3
```

#### Output:
```
1219
```

#### Explanation

Removing digits **4, 3, and 2** results in `1219`, which is the smallest possible number.

### Example 2

#### Input:
```
n = 10200, k = 1
```

#### Output:
```
200
```

#### Explanation

Removing **1** results in `0200`, which becomes `200` after trimming leading zeros.

### Approach

Use a **greedy approach with a monotonic stack**:

1. Iterate through the digits, maintaining a stack.
2. If the current digit is smaller than the top of the stack, pop from the stack (while `k` is not zero).
3. Push the current digit to the stack.
4. If any removals remain after iteration, remove from the top of the stack.
5. Rebuild the number from the stack and strip leading zeros.

---

## Interview Outcome

I cleared both rounds and was scheduled for a **third-round interview** with **Chirag Goel**, an Engineering Manager at Microsoft.

But just before the interview, I was informed that they had decided to **fill the role internally**. A little disappointing, but that’s how things go sometimes.

---

## Reflection

Even though I didn’t get to complete the process, it was a great experience. The interview challenged me, helped sharpen my **problem-solving** and **time management** skills, and gave me more confidence heading into future interviews.

On to the next opportunity! 🚀

