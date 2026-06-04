# Why These Skills Exist

Most candidates learn **algorithms**.

Top engineers learn **how to discover algorithms**.

The difference is not knowing 500 problems.

The difference is recognizing:

* What can never change? → Invariant
* What is actually restricting me? → Constraint
* What information is truly necessary? → State Compression
* What objective am I optimizing? → Optimization Reasoning

These four skills are the engine behind solving unseen problems.

---

# The Dependency Graph

Learn in this order:

```text
Constraint Analysis
       ↓
Invariant Discovery
       ↓
State Modeling
       ↓
State Compression
       ↓
Optimization Reasoning
       ↓
Algorithm Design
```

Why?

You cannot find invariants until you understand constraints.

You cannot compress state until you know what state matters.

You cannot optimize until you know the state space.

---

# Chapter 1 — Constraint Analysis

## Why should you care?

Every problem is secretly defined by constraints.

Most beginners focus on:

```text
What can I do?
```

Experts focus on:

```text
What am I NOT allowed to do?
```

The constraint usually reveals the solution.

---

## Section 1.1 — Hard Constraints

Learn to identify:

### Capacity Constraints

Examples:

```text
Memory limit
Time limit
Bandwidth
Weight
Size
```

Questions:

```text
What resource is scarce?
```

Examples:

* Knapsack
* CPU scheduling
* Cache eviction

---

### Ordering Constraints

Examples:

```text
Must happen before
Cannot happen after
Must preserve order
```

Problems:

* Topological Sort
* Task Scheduling
* Course Schedule

Signal:

```text
Dependency Graph
```

---

### Reachability Constraints

Examples:

```text
Can I reach destination?
Can I transform A → B?
```

Problems:

* BFS
* DFS
* Graph traversal

Signal:

```text
State Space
```

---

### Local Constraints

Examples:

```text
Adjacent only
Neighbor only
Window only
```

Problems:

* Sliding Window
* Two Pointers

Signal:

```text
Local interactions
```

---

### Global Constraints

Examples:

```text
Entire array
Whole graph
Whole schedule
```

Problems:

* DP
* Greedy Proofs

Signal:

```text
Need global information
```

---

## Section 1.2 — Constraint Extraction Practice

For every problem ask:

```text
What is limited?

What is fixed?

What can move?

What cannot move?

What operation is allowed?

What operation is forbidden?
```

Do this for 100 problems.

---

# Capability Unlocked

You stop guessing algorithms.

You start predicting them.

---

# Chapter 2 — Invariant Discovery

## Why should you care?

An invariant is the thing that survives all operations.

If you find it:

```text
Problem difficulty drops dramatically.
```

---

## Section 2.1 — Conservation Invariants

Examples:

### Sum Preserved

```text
Move coins
Transfer energy
Swap elements
```

Invariant:

```text
Total sum
```

---

### Parity Preserved

Examples:

```text
Flip 2 bits
Swap positions
Move by 2
```

Invariant:

```text
Even/Odd
```

Problems:

* Bulb switching
* Chessboard coloring

---

### Count Preserved

Examples:

```text
Swap only
Rearrange only
```

Invariant:

```text
Frequency map
```

Problems:

* Anagrams
* Permutations

---

## Section 2.2 — Structural Invariants

Examples:

### Relative Order

```text
Stack
Queue
Monotonic Structure
```

Invariant:

```text
Ordering relationship
```

---

### Connectivity

Graphs:

```text
Connected components
```

Invariant:

```text
Reachability group
```

---

## Section 2.3 — Mathematical Invariants

Learn:

* Modulo
* XOR
* GCD
* Parity
* Prefix Sum

These appear repeatedly in interview puzzles.

---

## Invariant Training

For every operation ask:

```text
What changes?

What never changes?
```

This question alone solves many hard problems.

---

# Capability Unlocked

You begin proving impossibility and deriving shortcuts.

---

# Chapter 3 — State Modeling

Before compression, learn state.

---

## Section 3.1 — What Is State?

State = minimum information needed to continue.

Example:

Fibonacci

```text
F(n)
```

Actually depends on:

```text
F(n-1)
F(n-2)
```

State:

```text
(n)
```

---

### Examples

Grid DP

```text
(row,col)
```

Stock DP

```text
(day,holding)
```

Knapsack

```text
(index,capacity)
```

---

## Section 3.2 — State Transition

Learn:

```text
Current State
     ↓
Operation
     ↓
Next State
```

Every DP is this.

Every graph search is this.

Every game search is this.

---

# Capability Unlocked

You can convert problems into state machines.

---

# Chapter 4 — State Compression

## Why should you care?

Many problems become easy when you realize most state is unnecessary.

---

## Section 4.1 — Dimension Reduction

Example:

Fibonacci

Instead of:

```text
dp[n]
```

Need only:

```text
prev
curr
```

Compression:

```text
O(n)
↓
O(1)
```

---

## Section 4.2 — Rolling States

Problems:

* Grid DP
* Edit Distance
* Unique Paths

Keep:

```text
Current row
Previous row
```

---

## Section 4.3 — Information Elimination

Ask:

```text
Will future decisions need this?
```

If no:

```text
Delete it.
```

---

## Section 4.4 — Bitmask Compression

Represent:

```text
Visited cities
Selected items
Used characters
```

as bits.

Learn:

```text
AND
OR
XOR
SHIFT
```

---

## Section 4.5 — Monotonic Structures

Compression through ordering.

Examples:

* Monotonic Stack
* Monotonic Queue

Store only useful candidates.

---

# Capability Unlocked

You reduce exponential state spaces into manageable ones.

---

# Chapter 5 — Optimization Reasoning

This is where most interview magic happens.

---

## Section 5.1 — Objective Function

Always identify:

```text
What exactly am I maximizing?

What exactly am I minimizing?
```

Examples:

```text
Cost
Distance
Profit
Time
Memory
```

---

## Section 5.2 — Greedy Exchange Argument

Learn:

```text
Why is local best globally best?
```

Classic examples:

* Activity Selection
* Huffman Coding
* Minimum Platforms

---

## Section 5.3 — Marginal Gain Thinking

Ask:

```text
If I spend one more unit,
what do I gain?
```

Appears in:

* Heap Problems
* Scheduling
* Resource Allocation

---

## Section 5.4 — Search Space Pruning

Ask:

```text
Can this branch ever beat current answer?
```

Examples:

* Branch and Bound
* Backtracking

---

## Section 5.5 — Monotonic Optimization

Signal:

```text
Answer space is ordered
```

Then:

```text
Binary Search on Answer
```

Examples:

* Koko Eating Bananas
* Ship Packages
* Aggressive Cows

---

## Section 5.6 — Dynamic Programming Optimization

Learn:

```text
Optimal Substructure
Overlapping Subproblems
```

Then:

```text
Memoization
Tabulation
State Compression
```

---

# Expert Pattern

For every unseen problem, run this checklist:

### Layer 1

```text
What is the constraint?
```

### Layer 2

```text
What never changes?
```

### Layer 3

```text
What state defines the future?
```

### Layer 4

```text
Can state be compressed?
```

### Layer 5

```text
What objective am I optimizing?
```

### Layer 6

```text
Is there monotonicity?
```

### Layer 7

```text
Can local decisions be proven optimal?
```

---

# Core Signal

Algorithms are not the real skill.

The real skill is extracting:

```text
Constraint
Invariant
State
Objective
```

Everything else is implementation.

# Highest Leverage Insight

Most hard interview problems become obvious once you identify the invariant and the minimum state.

# System Model

```text
Constraint
   ↓
Invariant
   ↓
State
   ↓
Compression
   ↓
Optimization
   ↓
Algorithm
```

# 3-Line Summary

Constraint analysis tells you what is possible.

Invariant discovery tells you what remains true.

State compression and optimization reasoning reveal the efficient solution.

# 1-Line Summary

Master the ability to see constraints, invariants, states, and objectives, and new algorithms will emerge naturally from the problem.

# Next Question

Would you like a **100-problem training roadmap** specifically organized by **Constraint Analysis → Invariant Discovery → State Compression → Optimization Reasoning**, with problems arranged from beginner to Google/Meta-level difficulty?
