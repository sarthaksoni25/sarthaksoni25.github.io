---
title: "Microsoft Interview Experience"
mathjax: true
layout: post
---

I recently had the opportunity to interview with Microsoft for an **SDE-2 position** in the **Ads team**. Below, I’ll walk through the problems I encountered and how I approached them.

## Round 1: Shipping Packages Within Days

### Problem Statement

You are given an array `weights` where `weights[i]` represents the weight of the `i`-th package. The task is to ship these packages within `days` days. Each day, you can ship a continuous subarray of packages, but the total weight on that day must not exceed a given capacity.

The goal is to find the **minimum capacity of a ship** such that all packages can be shipped within `days` days.

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

### Explanation:

A valid way to ship the packages in **5 days** with a ship of capacity **15** is:

- **Day 1**: `[1, 2, 3, 4, 5]` (Total = 15)
- **Day 2**: `[6, 7]` (Total = 13)
- **Day 3**: `[8]` (Total = 8)
- **Day 4**: `[9]` (Total = 9)
- **Day 5**: `[10]` (Total = 10)

### Approach

This problem can be efficiently solved using **Binary Search on the ship's capacity**:

- **Lower bound**: The heaviest package (since the ship must at least carry this).
- **Upper bound**: The sum of all package weights (i.e., shipping all in one day).
- **Binary Search**:
  - Check if a mid-value can be a feasible capacity.
  - If yes, try a smaller capacity.
  - Otherwise, increase the capacity.

This approach efficiently finds the **minimum possible capacity** to ship all packages in the given number of days.

---

## Round 2: Removing K Digits to Form the Smallest Number

### Problem Statement

Given a number `n` and an integer `k`, remove `k` digits from `n` to form the **smallest possible number** while preserving the **relative order of digits**.

### Example

#### Example 1

##### Input:

```
n = 1432219, k = 3;
```

##### Expected Output:

```
1219
```

##### Explanation:

Removing the digits **4, 3, and 2** results in `1219`, which is the smallest possible number.

#### Example 2

##### Input:

```
n = 10200, k = 1;
```

##### Expected Output:

```
200
```

##### Explanation:

Removing **1** results in `0200`, which becomes `200` after removing leading zeros.

### Approach

This problem is best solved using a **Greedy approach with a Monotonic Stack**:

1. **Iterate through the digits** of `n`, maintaining a stack.
2. **If the current digit is smaller than the top of the stack**, remove the top element (until `k` digits are removed).
3. **Push the current digit onto the stack**.
4. If there are remaining `k` removals, **remove from the top** of the stack.
5. **Convert the stack back into a number**, ensuring leading zeros are removed.

---

## My Interview Outcome

I cleared both rounds and was all set for my **third-round interview** with **Chirag Goel**, an **Engineering Manager at Microsoft**. 

But just before the interview, I got the news that **they had decided to fill the role internally**. A bit disappointing, but that’s how things go sometimes. 

---

## Reflection

Even though I didn’t get to complete the process, it was still a great experience. The interview challenged me, helped me refine my **problem-solving** and **time-management** skills, and gave me more confidence for the next opportunity.  

On to the next challenge! 🚀