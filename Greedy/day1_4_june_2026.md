# Greedy vs Dynamic Programming (DP)

## Core Idea

Optimization problems often contain many possible future decisions.

Example:

* 10 decisions, 2 choices each → 2¹⁰ = 1024 possible futures
* 50 decisions, 2 choices each → 2⁵⁰ ≈ 1 quadrillion possible futures

The challenge is finding the optimal answer without exploring unnecessary possibilities.

---

# Dynamic Programming (DP)

## Mental Model

DP assumes that a locally best decision may not lead to the globally optimal answer.

Therefore:

1. Explore all meaningful choices.
2. Build a decision tree.
3. Compute the best answer for every state.
4. Reuse previously computed states (memoization/tabulation).
5. Choose the optimal answer among all possibilities.

## Visualization

```text
Start
├── Choice A
│   ├── ...
│   └── ...
│
├── Choice B
│   ├── ...
│   └── ...
│
└── Choice C
    ├── ...
    └── ...
```

DP conceptually evaluates all branches but avoids recomputation by caching repeated states.

## DP Signal

* Multiple future paths exist.
* Current decision can affect future decisions.
* Local optimum may destroy global optimum.
* Same states appear repeatedly.
* Need the best answer among all possible paths.

## Definition

DP = Compare results from multiple possible futures and store intermediate results to obtain the global optimum.

---

# Greedy

## Mental Model

Greedy assumes that the best local decision also contributes to the best global solution.

Therefore:

1. Look at available choices.
2. Select the locally best choice.
3. Commit to it permanently.
4. Never revisit previous decisions.

## Visualization

```text
Start
├── A
├── B
├── C
└── D

Choose A

Done.
```

All other branches are discarded immediately.

## Greedy Signal

* Huge search space.
* A simple ranking exists.
* Local best choice is guaranteed to help globally.
* No need to revisit previous decisions.
* No overlapping subproblems.
* Current choice naturally creates the optimal future.

## Definition

Greedy = Continuously choose the locally optimal option and commit to it permanently.

---

# Key Difference

## DP

```text
Explore many futures
↓
Compare outcomes
↓
Choose global optimum
```

Question:

"Which future gives the best result?"

---

## Greedy

```text
Choose best now
↓
Commit
↓
Move forward
```

Question:

"Can I trust the current best choice to lead to the optimal answer?"

---

# Interview Detection

## Strong Greedy Signals

* Earliest finish time
* Highest profit per unit
* Smallest cost
* Largest value first
* Nearest choice
* Sort + choose

Examples:

* Activity Selection
* Jump Game
* Gas Station
* Huffman Coding
* Kruskal's MST
* Dijkstra (non-negative weights)

---

## Strong DP Signals

* Multiple choices at every step
* Need maximum/minimum answer
* Repeated states
* Current decision affects future options
* Greedy can fail

Examples:

* House Robber
* Coin Change
* Longest Common Subsequence
* Edit Distance
* Knapsack
* Climbing Stairs

---

# One-Line Rule

Greedy:

"Choose the next best hope."

DP:

"Compare all meaningful futures and select the best outcome."

---

# Ultimate Interview Question

Ask:

Can a locally optimal choice ever hurt me later?

If NO → Greedy candidate.

If YES → DP candidate.
