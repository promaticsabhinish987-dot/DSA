If your goal is **MAANG-level Greedy mastery**, don't solve random greedy problems.

The skill is not "learning greedy algorithms."

The skill is:

> **Finding the local decision that guarantees the globally optimal result.**

Most candidates fail because they memorize solutions instead of recognizing the pattern.

---

# Why Should You Care?

Greedy appears everywhere:

* Scheduling systems
* Resource allocation
* Network routing
* Compression
* Trading systems
* Interview problems

Capability unlocked:

* Turn O(2ⁿ) thinking into O(n log n)
* Spot optimal decisions quickly
* Reduce search space dramatically

Mistake avoided:

* Trying every possibility when a proof exists that one choice is always best.

---

# Greedy Pattern Roadmap

Master these patterns in order.

---

# Chapter 1 — Sort Then Decide

Signal:

> After sorting, the optimal choice becomes obvious.

Questions:

| LC   | Problem                                   |
| ---- | ----------------------------------------- |
| 455  | Assign Cookies                            |
| 2410 | Maximum Matching of Players With Trainers |
| 1710 | Maximum Units on a Truck                  |
| 2576 | Find Maximum Number of Marked Indices     |
| 1094 | Car Pooling                               |

Learn:

* Sort
* Process left→right
* Take best available option

---

# Chapter 2 — Interval Greedy

Signal:

> Intervals overlap.

Questions:

| LC   | Problem                                    |
| ---- | ------------------------------------------ |
| 435  | Non-overlapping Intervals                  |
| 452  | Minimum Number of Arrows to Burst Balloons |
| 646  | Maximum Length of Pair Chain               |
| 1288 | Remove Covered Intervals                   |
| 1024 | Video Stitching                            |

Invariant:

Keep interval ending earliest.

Why?

Earlier finish leaves maximum room for future intervals.

---

# Chapter 3 — Activity Selection

Signal:

> Choose maximum tasks/events.

Questions:

| LC   | Problem                                       |
| ---- | --------------------------------------------- |
| 1353 | Maximum Number of Events That Can Be Attended |
| 630  | Course Schedule III                           |
| 502  | IPO                                           |
| 857  | Minimum Cost to Hire K Workers                |

Learn:

* Earliest finish
* Highest profit
* Deadline constraints

---

# Chapter 4 — Jump Greedy

Signal:

> Reach destination with minimum jumps.

Questions:

| LC   | Problem       |
| ---- | ------------- |
| 55   | Jump Game     |
| 45   | Jump Game II  |
| 1306 | Jump Game III |
| 1345 | Jump Game IV  |

Invariant:

Maintain farthest reachable position.

---

# Chapter 5 — Gas Station Pattern

Signal:

> Circular route.

Questions:

| LC  | Problem     |
| --- | ----------- |
| 134 | Gas Station |
| 135 | Candy       |

Learn:

* Prefix deficits
* Restart strategy

Very common interview insight.

---

# Chapter 6 — Frequency Greedy

Signal:

> Most frequent element matters.

Questions:

| LC   | Problem                           |
| ---- | --------------------------------- |
| 621  | Task Scheduler                    |
| 767  | Reorganize String                 |
| 1405 | Longest Happy String              |
| 358  | Rearrange String k Distance Apart |

Learn:

* Always consume highest frequency first.

---

# Chapter 7 — Heap-Based Greedy

Signal:

> Need best available option at every step.

Questions:

| LC   | Problem                         |
| ---- | ------------------------------- |
| 215  | Kth Largest Element             |
| 973  | K Closest Points                |
| 1046 | Last Stone Weight               |
| 871  | Minimum Refueling Stops         |
| 1642 | Furthest Building You Can Reach |

Learn:

Heap = greedy data structure.

---

# Chapter 8 — Greedy With Proof

Signal:

> Greedy looks suspicious but works.

Questions:

| LC  | Problem                    |
| --- | -------------------------- |
| 763 | Partition Labels           |
| 738 | Monotone Increasing Digits |
| 649 | Dota2 Senate               |
| 678 | Valid Parenthesis String   |
| 991 | Broken Calculator          |

These teach:

* Exchange Argument
* Staying Ahead Proof
* Cut Property

The real heart of greedy.

---

# Chapter 9 — Hard Greedy

Questions:

| LC   | Problem                                   |
| ---- | ----------------------------------------- |
| 321  | Create Maximum Number                     |
| 330  | Patching Array                            |
| 630  | Course Schedule III                       |
| 871  | Minimum Refueling Stops                   |
| 1354 | Construct Target Array With Multiple Sums |
| 1402 | Reducing Dishes                           |
| 1665 | Minimum Initial Energy to Finish Tasks    |

These are interview-level greedy proofs.

---

# Expert Training Method

For every greedy problem ask:

### Question 1

What decision is made repeatedly?

Example:

* Choose interval
* Choose worker
* Choose jump

---

### Question 2

What state summarizes the past?

Example:

* farthestReach
* currentEnd
* currentFuel
* previousEnd

---

### Question 3

Why is this local choice safe?

This is the key.

Can I prove:

> Any optimal solution can be transformed into one using my choice?

If yes:

You found the greedy.

---

# 20-Problem Core Greedy List

Solve in this exact order:

1. LC 455 Assign Cookies
2. LC 860 Lemonade Change
3. LC 605 Can Place Flowers
4. LC 55 Jump Game
5. LC 45 Jump Game II
6. LC 435 Non-overlapping Intervals
7. LC 452 Minimum Arrows
8. LC 134 Gas Station
9. LC 135 Candy
10. LC 763 Partition Labels
11. LC 406 Queue Reconstruction
12. LC 621 Task Scheduler
13. LC 767 Reorganize String
14. LC 646 Pair Chain
15. LC 1024 Video Stitching
16. LC 871 Minimum Refueling Stops
17. LC 502 IPO
18. LC 630 Course Schedule III
19. LC 330 Patching Array
20. LC 1402 Reducing Dishes

---

## Core Signal

Greedy succeeds when a **local decision preserves the possibility of the global optimum**.

## Highest Leverage Insight

Most greedy problems reduce to maintaining a small state variable:

* farthest reach
* earliest ending interval
* remaining fuel
* current frequency

and updating it optimally at each step.

## System Model

```
Problem
   ↓
Find repeated decision
   ↓
Find state variable
   ↓
Find safest local choice
   ↓
Prove choice cannot hurt future
   ↓
Greedy solution
```

## 3-Line Summary

Greedy is not about being fast; it is about proving a local choice is safe.

Most greedy problems involve intervals, frequencies, reachability, or resource allocation.

The real skill is identifying the invariant that remains optimal after every decision.

## 1-Line Summary

Greedy = "Make the best move now, and prove future optimality is preserved."

## Next Question

Would you like a **Greedy Pattern Recognition Cheat Sheet** that lets you identify the correct greedy strategy within 30 seconds of reading a new problem?
