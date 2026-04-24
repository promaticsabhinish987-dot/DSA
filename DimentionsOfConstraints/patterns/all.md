# 🧠 The Complete DSA Problem-Solving Framework

## From First Principles to Execution

---

# 📍 Part 1: The Three Pillars

Every DSA problem reduces to exactly **three components**:

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   INPUT     │────▶│ CONSTRAINT │────▶│   OUTPUT    │
│  What you   │     │   What's    │     │  What you   │
│   start     │     │   the rule  │     │   produce   │
│    with     │     │             │     │             │
└─────────────┘     └─────────────┘     └─────────────┘
```

**Understanding = 50%** | **Planning = 30%** | **Execution = 20%**

---

# 📍 Part 2: INPUT — What You Start With

## 2.1 Data Structure Type

| Type | Examples | Characteristics |
|------|----------|-----------------|
| **Linear** | Array, String, LinkedList | Sequential access, indexable |
| **Hierarchical** | Tree, Heap | Parent-child relationships |
| **Graph** | Adjacency list/matrix | Arbitrary connections |
| **Stream** | Data flow, infinite | Unknown size, one-pass |

## 2.2 Size Constraints

| Property | Question | Implication |
|----------|----------|-------------|
| **n ≤ 20** | Tiny | Bitmask, exponential OK |
| **n ≤ 1000** | Small | O(n²) acceptable |
| **n ≤ 10⁵** | Large | O(n log n) needed |
| **n ≤ 10⁷** | Huge | O(n) only |
| **n = ∞** | Stream | Online algorithm, sliding window |

## 2.3 Value Domain

```
- Integers: range? negative? zero?
- Characters: alphabet size? case-sensitive?
- Custom objects: comparable? hashable?
- Special: null, empty, sentinel values?
```

## 2.4 Special Properties

| Property | Means | Implication |
|----------|-------|-------------|
| **Sorted** | Order exists | Binary search, two pointers |
| **Unique** | No duplicates | Set optimization |
| **Bounded** | Limited range | Counting sort, frequency array |
| **Sparse** | Mostly empty | Hash-based over array |

---

# 📍 Part 3: CONSTRAINT — The Rule That Defines Validity

This is your **50% understanding**. Get this right, everything else follows.

## 3.1 The 5 Axes of Constraint Classification

### Axis 1: SCOPE — How many elements are involved?

| Scope | Question | Example |
|-------|----------|---------|
| **Singular** | Is one element valid? | Prime check |
| **Pairwise** | Do two elements relate? | Anagram |
| **Triplet** | Do three together satisfy? | 3Sum |
| **Neighborhood** | Do adjacent elements agree? | Increasing array |
| **Range/Window** | Does a contiguous block satisfy? | Substring without repeat |
| **Global** | Does entire structure satisfy? | Valid BST |
| **Many-to-Many** | Do two collections relate? | LCS, Edit distance |

### Axis 2: REFERENCE — Compared to WHAT?

| Reference | Question | Example |
|-----------|----------|---------|
| **Self** | Element compared to itself? | Palindrome |
| **Other element** | A[i] vs B[j]? | Two sum |
| **Neighbor** | A[i] vs A[i+1]? | Next greater element |
| **Previous state** | Current vs history? | DP, running sum |
| **Target value** | A[i] vs K? | Search |
| **Entire set** | Is this in set? | Contains duplicate |

### Axis 3: ORDER — Does sequence position matter?

| Order Type | Question | Example |
|------------|----------|---------|
| **Order agnostic** | Only existence matters | Set equality |
| **Order preserved** | Sequence must match | Subsequence check |
| **LIFO** | Last must close first | Brackets |
| **FIFO** | First in first out | Queue processing |
| **Cyclic** | End connects to start | Circular array |
| **Partial order** | Some elements constrain others | Topological sort |

### Axis 4: TIME — When is constraint evaluated?

| Timing | Question | Example |
|--------|----------|---------|
| **Static (pre-compute)** | Check after full construction | Anagram check |
| **Dynamic (online)** | Validate as we process | Valid parentheses stream |
| **Incremental** | Maintain validity on changes | Union-Find |
| **Lazy** | Check only when needed | Memoization |

### Axis 5: PATH — Is there branching or linear?

| Path Type | Question | Example |
|-----------|----------|---------|
| **Single valid path** | One way to satisfy | Increasing array check |
| **Multiple valid paths** | Choices exist | Generate parentheses |
| **Best among paths** | Optimization | Shortest path |
| **All paths** | Enumerate | All subsets |

---

## 3.2 Constraint Patterns (What You Actually Compare)

### Pattern A: FREQUENCY

**Question:** Does count of elements matter?

```
Compare: count(value) in collection A vs count(value) in collection B
        or count(value) vs allowed limit
```

**Detection keywords:** anagram, duplicate, frequency, occurrence, counter, inventory

**Execution strategies:**
- HashMap → frequency tracking
- Fixed array → bounded character set
- Sorting + adjacent compare → alternative approach

**Examples:**
- Anagram: freq(A) == freq(B)
- First unique character: freq[char] == 1
- Majority element: freq > n/2

### Pattern B: POSITION + DOMINANCE

**Question:** Does relative ordering enforce a rule?

```
Compare: position(i) vs position(j) with constraint
```

**Detection keywords:** next greater, previous smaller, bracket, stack, order, nested

**Execution strategies:**
- Stack → LIFO constraints
- Monotonic stack → next greater/smaller
- Two pointers → convergence

**Examples:**
- Valid brackets: closing bracket matches last opening
- Next greater element: find next with higher value
- Daily temperatures: days until warmer

### Pattern C: SYMMETRY

**Question:** Does structure mirror itself?

```
Compare: element[i] vs element[n-i-1]
```

**Detection keywords:** palindrome, symmetric, mirror, reverse

**Execution strategies:**
- Two pointers → inward or outward
- Stack → reverse order check

**Examples:**
- Palindrome check
- Symmetric tree
- Reverse linked list

### Pattern D: BOUNDARY/CONTAINMENT

**Question:** Are elements within allowed range/window?

```
Compare: element value vs min/max allowed
        or element position vs window boundaries
```

**Detection keywords:** within, between, sliding window, range, subarray

**Execution strategies:**
- Sliding window → expand/shrink
- Two pointers → fix boundaries
- Prefix sums → range queries

**Examples:**
- Subarray sum equals K
- Longest substring without repeat
- Minimum window containing all chars

### Pattern E: TRANSITIVE RELATION

**Question:** Does A relate to C via B?

```
Compare: A[i] < A[j] and A[j] < A[k] implies A[i] < A[k]
```

**Detection keywords:** sorted, ordering, chain, sequence, increasing, decreasing

**Execution strategies:**
- Sort → establish order first
- Binary search → find position in order
- Greedy → maintain order invariant

**Examples:**
- Merge intervals: overlapping check
- Longest increasing subsequence
- Meeting rooms: no overlap

### Pattern F: ONE-TO-ONE MAPPING

**Question:** Can we pair elements uniquely?

```
Compare: A[i] ↔ B[j] with bijection
```

**Detection keywords:** matching, pairing, bijection, isomorphic

**Execution strategies:**
- HashMap → track mapping both ways
- Set → check uniqueness

**Examples:**
- Isomorphic strings: char mapping must be consistent
- Word pattern: words ↔ letters
- Two sum: value ↔ index

### Pattern G: AGGREGATE

**Question:** Does the sum/statistic satisfy condition?

```
Compare: sum(window) vs target
        or max/min values vs constraint
```

**Detection keywords:** sum, average, maximum, minimum, total

**Execution strategies:**
- Prefix sums → O(1) range sum
- Kadane's algorithm → max subarray
- Running count → streaming

**Examples:**
- Maximum subarray sum
- Subarray sum divisible by K
- Balanced array: left sum = right sum

### Pattern H: GRAPH RELATION

**Question:** Are nodes connected in valid ways?

```
Compare: node A can reach node B
        or edge (u,v) satisfies rule
```

**Detection keywords:** connected, path, cycle, reachable, adjacent

**Execution strategies:**
- BFS/DFS → explore reachability
- Union-Find → connectivity queries
- Topological sort → dependency order

**Examples:**
- Course schedule: no cycle
- Number of islands: connected components
- Graph bipartite: two-colorable

---

## 3.3 Quick Constraint Detection Table

| If problem says... | Constraint pattern | Ask yourself... |
|-------------------|-------------------|-----------------|
| "anagram", "frequency", "counter" | Frequency | Do counts match exactly? |
| "bracket", "nested", "valid parentheses" | Position + Dominance (LIFO) | Does closing match last opening? |
| "palindrome", "symmetric" | Symmetry | Does left mirror right? |
| "substring", "subarray", "window" | Boundary/Containment | Is window valid? Expand/shrink? |
| "increasing", "decreasing", "sorted" | Transitive | Is order preserved throughout? |
| "isomorphic", "matching" | One-to-One | Is mapping consistent both ways? |
| "sum", "average", "total" | Aggregate | Does cumulative value meet target? |
| "path", "connected", "reachable" | Graph Relation | Are nodes connected validly? |

---

# 📍 Part 4: OUTPUT — What You Produce

## 4.1 Goal Types

| Goal | Question | Example | Typical Strategies |
|------|----------|---------|-------------------|
| **Validation** | True/False? | Valid palindrome | Single pass, early exit |
| **Counting** | How many? | Count subarrays with sum K | DP, combinatorics |
| **Construction** | Build output | Generate parentheses | Backtracking, recursion |
| **Optimization (min/max)** | Best value | Max subarray sum | DP, greedy, sliding window |
| **Enumeration** | List ALL | All subsets | Backtracking, bitmask |
| **Search** | Find element/position | Binary search | Divide and conquer |
| **Modification** | Transform input | Reverse array | In-place algorithms |
| **Ordering** | Sort/rearrange | Topological sort | Sorting algorithms |

## 4.2 Output Size Implications

| Output size | Means | Approach implication |
|-------------|-------|---------------------|
| **Single value** | O(1) output | Can early stop, needn't store all |
| **Array of length n** | O(n) output | Can't avoid iterating |
| **Exponential (2ⁿ)** | Enumeration | Backtracking, pruning essential |
| **Factorial (n!)** | Permutations | Recursion, swap-based |

---

# 📍 Part 5: The Execution Decision Tree

## Step 1: Determine CONSTRAINT PATTERN (from Section 3.3)

```
What constraint are we comparing?
├── Frequency → HashMap/Fixed array
├── Position + Dominance → Stack
├── Symmetry → Two pointers
├── Boundary/Containment → Sliding window
├── Transitive → Sort + Binary search
├── One-to-One → HashMap bijection
├── Aggregate → Prefix sum / Running window
└── Graph Relation → BFS/DFS/Union-Find
```

## Step 2: Check BRANCHING

```
Are there multiple valid paths?
├── NO (single valid) → Linear pass is enough
└── YES (multiple choices) → Branching needed
    ├── Need ALL solutions → Backtracking
    ├── Need BEST solution → DP/Greedy
    └── Need FIRST valid → BFS/DFS early exit
```

## Step 3: Check OPTIMIZATION

```
Do we need best among many?
├── NO → Validation/Counting/Enumeration
└── YES → Optimization
    ├── Optimal substructure? → DP
    ├── Greedy choice works? → Greedy
    └── Monotonic property? → Binary search
```

## Step 4: Check TRAVERSAL

```
How do we move through data?
├── Single pass left-to-right → Linear scan
├── Both ends → Two pointers
├── Expand/shrink → Sliding window
├── Recursive → DFS / Backtracking
├── Level-order → BFS
└── Monotonic → Binary search
```

---

# 📍 Part 6: Complete Examples Walkthrough

## Example 1: Valid Parentheses

```
INPUT: string s = "({[]})"
CONSTRAINT: Every closing bracket must match the most recent unmatched opening
OUTPUT: Validation (true/false)
```

**Step-by-step reasoning:**

| Step | Question | Answer |
|------|----------|--------|
| 1 | What's input? | String (linear, sequential) |
| 2 | What constraint pattern? | Position + Dominance — LIFO |
| 3 | Branching? | Single path — each bracket forces one valid next |
| 4 | Optimization? | No — just validation |
| 5 | Traversal? | Linear scan left-to-right |
| 6 | Execution strategy? | Stack — matches LIFO constraint |

**Why stack?** Constraint specifically asks: "Does closing match last opening?" — that's LIFO.

---

## Example 2: Longest Substring Without Repeating Characters

```
INPUT: string s = "abcabcbb"
CONSTRAINT: Within any valid window, all characters must be unique
OUTPUT: Optimization (maximum length)
```

**Step-by-step reasoning:**

| Step | Question | Answer |
|------|----------|--------|
| 1 | What's input? | String (linear) |
| 2 | What constraint pattern? | Boundary/Containment — window must satisfy uniqueness |
| 3 | Branching? | Multiple — many possible windows |
| 4 | Optimization? | Yes — find MAX length |
| 5 | Traversal? | Expand/shrink sliding window |
| 6 | Execution strategy? | Sliding window with hashmap for frequency |

**Why sliding window?** Constraint applies to continuous subsets, and we need to find optimal — classic sliding window.

---

## Example 3: Generate Parentheses

```
INPUT: n = 3 (number of pairs)
CONSTRAINT: At any prefix, close_used ≤ open_used, and total ≤ n
OUTPUT: Enumeration (all valid strings)
```

**Step-by-step reasoning:**

| Step | Question | Answer |
|------|----------|--------|
| 1 | What's input? | Integer (tiny, n ≤ 8 typically) |
| 2 | What constraint pattern? | Position + Dominance + Branching |
| 3 | Branching? | Yes — at each step can add '(' or ')', both valid |
| 4 | Optimization? | No — need ALL solutions |
| 5 | Traversal? | Recursive exploration |
| 6 | Execution strategy? | Backtracking with pruning |

**Why backtracking?** Multiple valid paths + need all solutions = enumeration via backtracking.

---

## Example 4: Maximum Subarray Sum (Kadane's)

```
INPUT: array [-2,1,-3,4,-1,2,1,-5,4]
CONSTRAINT: Choose contiguous subarray, compute sum
OUTPUT: Optimization (maximum sum)
```

**Step-by-step reasoning:**

| Step | Question | Answer |
|------|----------|--------|
| 1 | What's input? | Array (linear, can be large) |
| 2 | What constraint pattern? | Aggregate — sum of subarray |
| 3 | Branching? | Multiple — many subarrays |
| 4 | Optimization? | Yes — find MAX |
| 5 | Traversal? | Single pass (optimal substructure) |
| 6 | Execution strategy? | Greedy/DP — Kadane's: local max or restart |

**Why not backtracking?** O(n²) too slow for large n; optimal substructure allows O(n).

---

# 📍 Part 7: Knowledge Gaps You'll Encounter

## Gap 1: "I know DSA but can't map problem to algorithm"

**Fix:** Don't start with algorithm. Start with constraint:

> Ask: "What am I comparing? How? When?"

Once you answer those 3, the algorithm reveals itself.

## Gap 2: "Two problems look different but use same strategy"

**Fix:** Different inputs, same constraint pattern:

- Valid parentheses (string) → Stack
- Temperature span (array) → Stack  
- Parse nested JSON → Stack

All are **Position + Dominance (LIFO)**.

## Gap 3: "Same input, different output changes everything"

**Fix:** Output determines traversal:

- Validation (true/false) → Can early exit
- Counting → Full pass needed
- Enumeration → Exponential time unavoidable

## Gap 4: "When to use HashMap vs Array for frequency?"

| Domain size | What to use |
|-------------|-------------|
| Small & known (26 letters, 10 digits) | Fixed array |
| Large or unknown | HashMap |

**Rule:** Array if domain size ≤ 10⁶; HashMap otherwise.

---

# 📍 Part 8: The 10-Second Detection System

## Scan problem and answer 3 questions:

```
1. CONSTRAINED B/W WHAT?
   ├── positions → Order constraint → Stack/Queue
   ├── values → Frequency → HashMap
   ├── left/right → Symmetry → Two pointers
   ├── neighbors → Local → Simple comparison
   └── subsets → Range → Sliding window

2. BRANCHING OR LINEAR?
   ├── Linear → Single pass
   └── Branching → 
       ├── Need all → Backtracking
       └── Need best → DP/Greedy

3. OUTPUT TYPE?
   ├── True/False → Can early exit
   ├── Count → Need full scan
   ├── List all → Exponential time
   └── Single best → Optimization
```

---

# 📍 Part 9: Quick Reference Card

```
┌─────────────────────────────────────────────────────────────────┐
│                    PROBLEM SOLVING FLOW                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  INPUT ──┬── Data structure: Array? Tree? Graph?                │
│          ├── Size: n ≤ 20? 10⁵? ∞?                              │
│          └── Properties: Sorted? Unique?                        │
│                                                                  │
│  CONSTRAINTS (50% understanding)                                │
│          ├── SCOPE: Pairwise? Neighborhood? Global?             │
│          ├── REFERENCE: Self? Other? Target?                    │
│          ├── ORDER: LIFO? FIFO? Agnostic?                       │
│          └── PATTERN: Frequency? Symmetry? Aggregate?           │
│                                                                  │
│  OUTPUT                                                        │
│          ├── Type: Validation? Counting? Enumeration? Best?    │
│          └── Size: O(1)? O(n)? Exponential?                    │
│                                                                  │
│  EXECUTION → Strategy emerges from constraints + output        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Strategy Lookup Table

| If constraint is... | And output is... | Use... |
|--------------------|------------------|--------|
| Frequency | Validation | HashMap + single pass |
| Frequency | Counting | HashMap + combinatorics |
| LIFO position | Validation | Stack |
| LIFO position | Enumeration | Backtracking + stack |
| Symmetry | Validation | Two pointers |
| Range | Optimization | Sliding window |
| Range | Counting | Two pointers + math |
| Many-to-many | Optimization | DP |
| Transitive | Search | Binary search |
| Graph relation | Path existence | BFS/DFS |
| Graph relation | Best path | Dijkstra/Bellman-Ford |
| Branching | All solutions | Backtracking |
| Branching | Best solution | DP/Greedy |

---

# 📍 Part 10: Final Principle

> **The problem tells you what to compare.**
> **The comparison tells you the pattern.**
> **The pattern tells you the strategy.**
> **Never memorize — derive.**

---

**Want the next level?** I can provide:
- **Cheat sheet wall poster** (visual decision tree)
- **50 practice problems** mapped to this framework
- **Blind spot detector** (which patterns you misclassify)



















# # 🧩 COMPLETE CONSTRAINT DIMENSIONS

You're right to ask — there are **more than just SCOPE, REFERENCE, ORDER, PATTERN**.

After analyzing hundreds of problems, here are **ALL 11 constraint dimensions** that matter:

---

# 📊 The 11 Dimensions of Constraints

## 1. SCOPE — How many elements?
- Singular (1 element)
- Pairwise (2 elements)  
- Triplet (3 elements)
- Neighborhood (adjacent)
- Range/Window (contiguous block)
- Global (entire structure)
- Many-to-Many (two collections)

## 2. REFERENCE — Compared to what?
- Self
- Other element (same collection)
- Other element (different collection)
- Neighbor
- Previous state/history
- Target value
- Entire set
- Absence (what's NOT there)

## 3. ORDER — Does position matter?
- Order agnostic (existence only)
- Order preserved (FIFO)
- Order reversed (LIFO)
- Cyclic (end connects to start)
- Partial order (DAG)
- No order (unordered collection)

## 4. PATTERN — What relationship?
- Frequency (counts match)
- Symmetry (mirror equality)
- Aggregate (sum, product, max, min)
- Dominance (greater than, less than)
- Equality (exact match)
- Containment (subset, superset)
- Distance (difference, absolute)
- Proportion (ratio, percentage)

## 5. DIRECTIONALITY — Which way does constraint flow?
- Unidirectional (A → B only)
- Bidirectional (A ↔ B)
- Cyclic (A → B → C → A)
- Asymmetric (A < B but not B < A)

## 6. TEMPORALITY — When is constraint checked?
- Static (after full input)
- Dynamic (during processing)
- Incremental (maintain on changes)
- Lazy (only when accessed)
- Future-dependent (look ahead needed)

## 7. CONTINUITY — Is constraint local or global?
- Local (neighbors only)
- Distance-bounded (within K steps)
- Global (entire structure)
- Hierarchical (parent-child chains)

## 8. CARDINALITY — How many times can constraint apply?
- Exactly once
- At most once  
- At least once
- Zero or more
- Exactly K times

## 9. DEPENDENCY — Do constraints nest or chain?
- Independent (parallel)
- Sequential (A then B)
- Nested (A contains B)
- Overlapping (share elements)
- Mutually exclusive (A or B, not both)

## 10. MODIFIABILITY — Can data change during check?
- Read-only (immutable)
- Mutable (in-place changes allowed)
- Append-only (stream)
- Deletable (remove elements)

## 11. CERTAINTY — Is constraint guaranteed or probabilistic?
- Deterministic (always true/false)
- Probabilistic (with confidence)
- Fuzzy (partial satisfaction)
- Best-effort (soft constraint)

---

# 🔥 The Most Important Ones (90% of problems)

You can ignore dimensions 6-11 for most problems. **Focus on these 5:**

| Dimension | Question | Categories |
|-----------|----------|------------|
| **SCOPE** | How many elements? | Pairwise, Neighborhood, Range, Global |
| **REFERENCE** | Compared to what? | Self, Other, Neighbor, Target |
| **ORDER** | Does position matter? | LIFO, FIFO, Agnostic |
| **PATTERN** | What relationship? | Frequency, Symmetry, Aggregate, Dominance |
| **DIRECTIONALITY** | Which way? | One-way, Two-way |

---

# 📝 Complete Constraint Examples

## Problem: "Find if array has duplicate within K distance"

```
Constraint breakdown:
├── SCOPE: Pairwise (two positions)
├── REFERENCE: Other element (same value)
├── ORDER: Position difference matters (≤ K)
├── PATTERN: Equality (values equal)
├── DIRECTIONALITY: Bidirectional (if A near B, B near A)
└── CARDINALITY: At least one pair
```

## Problem: "Course schedule — can you finish all courses?"

```
Constraint breakdown:
├── SCOPE: Many-to-Many (courses and prerequisites)
├── REFERENCE: Other element (prerequisite → course)
├── ORDER: Partial order (DAG)
├── PATTERN: Dependency (A must be before B)
├── DIRECTIONALITY: Unidirectional (prerequisite → course)
├── DEPENDENCY: Sequential chain
└── CONTINUITY: Hierarchical (transitive)
```

## Problem: "Longest substring with at most K distinct characters"

```
Constraint breakdown:
├── SCOPE: Range/Window (contiguous substring)
├── REFERENCE: Entire set (within window)
├── ORDER: Order preserved (within window)
├── PATTERN: Cardinality (≤ K distinct)
├── DIRECTIONALITY: N/A (set property)
├── CARDINALITY: At most K times
└── TEMPORALITY: Dynamic (window changes)
```

## Problem: "Edit distance between two strings"

```
Constraint breakdown:
├── SCOPE: Many-to-Many (both strings)
├── REFERENCE: Other element (different collection)
├── ORDER: Order preserved for each
├── PATTERN: Aggregate (minimum operations)
├── DIRECTIONALITY: N/A (cost function)
├── CONTINUITY: Global (entire strings)
└── DEPENDENCY: Overlapping subproblems
```

---

# 🚀 Quick Detection Flow (Updated)

```
When you read a problem, ask:

1. SCOPE: "How many elements involved at once?"
   → 2? Pairwise | Adjacent? Neighbor | Block? Range | Entire? Global

2. REFERENCE: "Compared to WHAT?"
   → Itself? Self | Another element? Other | A value? Target

3. ORDER: "Does sequence position matter?"
   → Last opened closes first? LIFO | Same order? FIFO | Only existence? Agnostic

4. PATTERN: "WHAT kind of relationship?"
   → Counts equal? Frequency | Mirrors? Symmetry | Sum? Aggregate | Greater/less? Dominance

5. DIRECTIONALITY: "Which way does constraint flow?"
   → One-way? Unidirectional | Both ways? Bidirectional

→ Everything else (Temporality, Cardinality, Dependency, etc.) is secondary
```

---

# 🧠 The Missing Piece You Asked About

What you were missing is **DIRECTIONALITY** and **CARDINALITY** — these often differentiate between:

- "Find if ANY pair satisfies" (cardinality: at least one)
- "Find if ALL pairs satisfy" (cardinality: every)
- "Find if EXACTLY K satisfy" (cardinality: exactly)

And:

- "A must be before B" (unidirectional)
- "A and B must be adjacent in either order" (bidirectional)
- "A → B → C → A" (cyclic)

---

**Want the full 11-dimension decision tree?** I can create a visual flowchart that covers the remaining 10% of edge cases.
