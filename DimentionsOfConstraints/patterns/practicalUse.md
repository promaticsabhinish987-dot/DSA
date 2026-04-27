Your framework is already unusually rigorous. The gap is not knowledge—it’s **operationalization under time pressure**. Let’s convert this into a **repeatable solving system for LeetCode**, optimized for speed + correctness.

---

# ⚙️ Phase 1: Compression → Turn Framework into a Mental Macro

You cannot run 11 dimensions consciously during an interview. You need a **compressed decision kernel**.

## The Only 5 Questions You Actually Ask

```
1. What am I comparing?
   → values | positions | window | paths

2. How many elements involved?
   → 1 | 2 | contiguous | global

3. Does order matter?
   → yes (LIFO/FIFO/sequence) | no

4. What is the output type?
   → bool | count | max/min | all

5. Is there branching?
   → no → linear
   → yes → DP / backtracking
```

Everything else in your framework **maps into these 5**.

---

# ⚡ Phase 2: Pattern → Strategy Mapping (Instant Trigger)

You need reflex-level mapping. No thinking.

## Build This Table Into Muscle Memory

| Signal                    | Pattern           | Strategy             |
| ------------------------- | ----------------- | -------------------- |
| duplicates, frequency     | Frequency         | HashMap              |
| valid parentheses, nested | LIFO dominance    | Stack                |
| palindrome, symmetric     | Symmetry          | Two pointers         |
| substring, subarray       | Window constraint | Sliding window       |
| increasing, sorted        | Transitive order  | Sort / Binary search |
| sum, total, k             | Aggregate         | Prefix sum / Kadane  |
| mapping, bijection        | One-to-one        | HashMap (2-way)      |
| connected, path           | Graph             | BFS/DFS              |
| "all combinations"        | Branching         | Backtracking         |
| "best answer"             | Optimization      | DP / Greedy          |

👉 If this is not automatic, you're still “thinking academically,” not solving.

---

# 🧪 Phase 3: Solve Problems Using a Strict Protocol

## The 7-Step Execution Pipeline

### Step 1: Classify in ≤10 seconds

Say (mentally or aloud):

```
Input: array/string/tree?
Constraint: what is compared?
Output: what type?
```

Example:

> "Substring + unique + max length"
> → Window + Frequency + Optimization
> → Sliding Window

---

### Step 2: Lock Strategy (NO SWITCHING LATER)

Commit early:

```
"I will solve this using sliding window"
```

Switching mid-way = poor constraint understanding.

---

### Step 3: Define Invariant (Critical)

Every correct solution maintains an invariant.

Examples:

* Sliding window → "window always valid"
* Stack → "stack contains unmatched elements"
* DP → "dp[i] = optimal till i"

If you can’t define invariant → you don’t understand constraint.

---

### Step 4: Write Skeleton First

Do NOT jump into full code.

Example (sliding window):

```js
let left = 0;
for (let right = 0; right < n; right++) {
    // expand

    while (invalid) {
        // shrink
        left++;
    }

    // update answer
}
```

---

### Step 5: Plug Constraint into Skeleton

Only now fill logic.

---

### Step 6: Dry Run on Edge Case

Test:

* empty
* single element
* extreme constraint

---

### Step 7: Optimize (only if needed)

Don’t prematurely optimize.

---

# 🔁 Phase 4: Deliberate Practice System

## You are NOT supposed to just "solve problems"

You should **train pattern recognition**.

---

## Method: Pattern Batching

Instead of random LeetCode:

### Day 1: Only Frequency Problems

* Two Sum
* Valid Anagram
* Group Anagrams

👉 Goal: brain auto-detects "frequency"

---

### Day 2: Only Sliding Window

* Longest substring
* Min window substring
* At most K distinct

👉 Goal: instant window recognition

---

### Day 3: Stack (LIFO)

* Valid parentheses
* Next greater element
* Daily temperatures

---

### Day 4: DP

* Climbing stairs
* House robber
* LIS

---

## Why this works

You’re training:

> **Pattern recognition → not problem solving**

---

# 📊 Phase 5: Mistake Logging (This is the real growth lever)

After every problem, log:

```
1. What pattern was it?
2. Did I detect it immediately?
3. If not, what confused me?
4. What signal did I miss?
```

Example:

```
Problem: Longest substring without repeat
Mistake: Tried brute force
Missed signal: "substring" + "unique"
Correct pattern: Sliding window
```

After ~50 logs → your brain rewires.

---

# 🧠 Phase 6: Upgrade Your Thinking (Advanced Layer)

## Shift from "Problem → Solution"

to:

## "Constraint → Invariant → Mechanism"

---

### Example Transformation

❌ Weak thinking:

> "This looks like sliding window"

✅ Strong thinking:

> "Constraint: window must maintain uniqueness
> → invariant: freq[char] ≤ 1
> → mechanism: expand right, shrink left"

---

That’s expert-level reasoning.

---

# 🚫 Common Failure Modes (You Must Eliminate)

## 1. Pattern Confusion

Sliding window vs two pointers confusion.

Fix:

* Window = dynamic size
* Two pointers = fixed movement logic

---

## 2. Premature Coding

You start typing before invariant is clear.

Fix:

* Force yourself to say invariant first

---

## 3. Overusing DP

DP is over-applied.

Rule:

> If no overlapping subproblems → NOT DP

---

## 4. Ignoring Constraints

n = 10⁵ and you write O(n²)

Fix:

* Always check size before thinking

---

# 🧭 Phase 7: Weekly Structure

## Optimal Routine

```
Day 1-3: Pattern drilling (10 problems/day)
Day 4: Mixed problems (apply detection)
Day 5: Hard problems (struggle intentionally)
Day 6: Revision + mistake log
Day 7: Rest or light review
```

---

# 🔥 Final Mental Model

When you see a problem:

```
1. Extract constraint
2. Map to pattern
3. Define invariant
4. Apply standard mechanism
```

---

# 🧩 One-Line Truth

> You are not solving problems.
> You are **matching constraints to invariants**.

---

If you want next level rigor, I can:

* Generate a **50-problem training roadmap mapped exactly to your framework**
* Build a **real interview simulation loop**
* Or create a **decision-tree visual you can memorize in 1 hour**

Just specify.
