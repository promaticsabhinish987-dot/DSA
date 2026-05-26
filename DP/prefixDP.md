# Prefix DP — From First Principles

Before solving questions, build the mental model.

---

# 1. What is Prefix DP?

## First Principle

A problem becomes **Prefix DP** when:

> "Answer for position `i` depends on answers from earlier positions `[0...i-1]`."

You progressively build knowledge from left → right.

Think of it like human memory:

* You do not recompute your entire life every day.
* You carry accumulated knowledge forward.

DP does the same.

---

# 2. Core Structure

Most prefix DP problems follow:

```js
dp[i] = best answer considering prefix ending at i
```

or

```js
dp[i] = combine(previous states)
```

---

# 3. Why Prefix?

Because we process array/string incrementally.

Example:

```txt
Index: 0 1 2 3 4
Array: 1 2 3 4 5
```

At position `4`,
you already know everything about `[0...3]`.

That previous knowledge becomes reusable state.

---

# 4. Main Patterns Inside Prefix DP

| Pattern             | Core Idea                              |
| ------------------- | -------------------------------------- |
| Linear Transition   | `dp[i]` depends on few previous states |
| Partition DP        | split prefix into segments             |
| Include / Exclude   | choose current or skip                 |
| Optimization        | min/max                                |
| Counting            | count ways                             |
| Prefix + HashMap    | optimize transitions                   |
| Monotonic Prefix DP | maintain best prefix state             |

---

# LEVEL 1 — BASIC PREFIX STATE

---

# Question 1 — Climbing Stairs

## Problem

You can climb:

* 1 step
* 2 steps

How many ways to reach `n`?

---

## First Principle

To reach stair `n`:

You came from:

* `n-1`
* `n-2`

So:

```txt
ways(n) = ways(n-1) + ways(n-2)
```

This is pure prefix accumulation.

---

## JS Solution

```js
function climbStairs(n) {
    const dp = new Array(n + 1).fill(0);

    dp[0] = 1;
    dp[1] = 1;

    for (let i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }

    return dp[n];
}
```

---

## Knowledge Gap You Learn

### Gap:

"Current state can be formed from previous states."

This is the birth of recurrence relation thinking.

---

---

# Question 2 — Min Cost Climbing Stairs

## Pattern

Optimization Prefix DP

---

## First Principle

At each stair:

You ask:

> "What is the cheapest way to reach here?"

---

## Transition

```txt
dp[i] = cost[i] + min(dp[i-1], dp[i-2])
```

---

## JS

```js
function minCost(cost) {
    const n = cost.length;
    const dp = new Array(n);

    dp[0] = cost[0];
    dp[1] = cost[1];

    for (let i = 2; i < n; i++) {
        dp[i] = cost[i] + Math.min(dp[i - 1], dp[i - 2]);
    }

    return Math.min(dp[n - 1], dp[n - 2]);
}
```

---

## Knowledge Gap

### New Idea:

DP is not only counting.

It can optimize:

* minimum
* maximum
* cheapest
* longest

---

# LEVEL 2 — INCLUDE / EXCLUDE PREFIX DP

---

# Question 3 — House Robber

## Problem

Cannot rob adjacent houses.

---

## First Principle

At house `i`:

Two choices:

| Choice | Meaning              |
| ------ | -------------------- |
| Skip   | use `dp[i-1]`        |
| Take   | money[i] + `dp[i-2]` |

---

## Transition

```txt
dp[i] = max(
    dp[i-1],
    nums[i] + dp[i-2]
)
```

---

## JS

```js
function rob(nums) {
    const n = nums.length;

    if (n === 1) return nums[0];

    const dp = new Array(n);

    dp[0] = nums[0];
    dp[1] = Math.max(nums[0], nums[1]);

    for (let i = 2; i < n; i++) {
        dp[i] = Math.max(
            dp[i - 1],
            nums[i] + dp[i - 2]
        );
    }

    return dp[n - 1];
}
```

---

## Knowledge Gap

### Major DP Skill:

Every DP state often represents:

> "Decision at current index."

This introduces:

* take / not take
* include / exclude

This becomes foundation for:

* knapsack
* subsequence
* stock DP
* interval DP

---

# LEVEL 3 — PREFIX + PARTITION

---

# Question 4 — Word Break

## Problem

Can string be segmented into dictionary words?

---

## First Principle

At position `i`:

We ask:

> "Can any earlier valid prefix connect to me?"

---

## Transition

```txt
dp[i] = true
if any j < i satisfies:

dp[j] === true
AND
s[j...i] exists in dictionary
```

---

## Visualization

```txt
leetcode

leet | code
```

If:

* `"leet"` valid
* `"code"` valid

then full prefix valid.

---

## JS

```js
function wordBreak(s, wordDict) {
    const set = new Set(wordDict);

    const dp = new Array(s.length + 1).fill(false);

    dp[0] = true;

    for (let i = 1; i <= s.length; i++) {

        for (let j = 0; j < i; j++) {

            const word = s.slice(j, i);

            if (dp[j] && set.has(word)) {
                dp[i] = true;
                break;
            }
        }
    }

    return dp[s.length];
}
```

---

## Knowledge Gap

### Huge Concept:

DP states can represent:

> "Validity of entire prefix."

Not numeric only.

DP can store:

* boolean
* count
* string
* object
* bitmask

---

# LEVEL 4 — COUNTING PREFIX DP

---

# Question 5 — Decode Ways

## Problem

`"226"`

Possible:

* 2 2 6
* 22 6
* 2 26

Answer = 3

---

## First Principle

At each index:

Ways come from:

* taking one digit
* taking two digits

---

## Transition

```txt
dp[i] =
ways from single digit
+
ways from double digit
```

---

## JS

```js
function numDecodings(s) {
    const n = s.length;

    const dp = new Array(n + 1).fill(0);

    dp[0] = 1;
    dp[1] = s[0] === '0' ? 0 : 1;

    for (let i = 2; i <= n; i++) {

        const one = Number(s.slice(i - 1, i));
        const two = Number(s.slice(i - 2, i));

        if (one >= 1) {
            dp[i] += dp[i - 1];
        }

        if (two >= 10 && two <= 26) {
            dp[i] += dp[i - 2];
        }
    }

    return dp[n];
}
```

---

## Knowledge Gap

### Advanced Transition Composition

One state may aggregate:

* multiple transition sources
* different step sizes
* different interpretations

---

# LEVEL 5 — PREFIX OPTIMIZATION DP

---

# Question 6 — Longest Increasing Subsequence (O(n²))

## First Principle

At index `i`:

Ask:

> "Which previous increasing subsequence can I extend?"

---

## Transition

```txt
dp[i] =
1 + max(dp[j])

where:
j < i
nums[j] < nums[i]
```

---

## JS

```js
function lengthOfLIS(nums) {
    const n = nums.length;

    const dp = new Array(n).fill(1);

    let ans = 1;

    for (let i = 0; i < n; i++) {

        for (let j = 0; j < i; j++) {

            if (nums[j] < nums[i]) {
                dp[i] = Math.max(
                    dp[i],
                    dp[j] + 1
                );
            }
        }

        ans = Math.max(ans, dp[i]);
    }

    return ans;
}
```

---

## Knowledge Gap

### Critical Shift

DP transitions may scan entire previous prefix.

Not only:

* `i-1`
* `i-2`

This creates:

* quadratic DP
* graph-like transitions

---

# LEVEL 6 — PREFIX + HASHMAP OPTIMIZATION

---

# Question 7 — Longest Arithmetic Subsequence

---

## First Principle

State now needs TWO dimensions:

```txt
dp[i][diff]
```

Meaning:

> longest arithmetic subsequence ending at i with difference diff

---

## Transition

If:

```txt
nums[i] - nums[j] = diff
```

Then:

```txt
dp[i][diff] =
dp[j][diff] + 1
```

---

## JS

```js
function longestArithSeqLength(nums) {
    const n = nums.length;

    const dp = Array.from(
        { length: n },
        () => new Map()
    );

    let ans = 2;

    for (let i = 0; i < n; i++) {

        for (let j = 0; j < i; j++) {

            const diff = nums[i] - nums[j];

            const prev = dp[j].get(diff) || 1;

            dp[i].set(diff, prev + 1);

            ans = Math.max(
                ans,
                dp[i].get(diff)
            );
        }
    }

    return ans;
}
```

---

## Knowledge Gap

### Massive DP Upgrade

State may require:

* index
* difference
* parity
* remaining capacity
* bitmask
* previous choice

This evolves into:

* multidimensional DP

---

# LEVEL 7 — HARDEST PREFIX DP

---

# Question 8 — Palindrome Partitioning II

## Problem

Minimum cuts needed so every partition is palindrome.

---

## First Principle

At index `i`:

We ask:

> "Which palindrome suffix can finish optimally here?"

---

## State

```txt
dp[i] =
minimum cuts needed for prefix [0...i]
```

---

## Transition

If substring `(j...i)` is palindrome:

```txt
dp[i] =
min(
    dp[i],
    dp[j-1] + 1
)
```

---

## JS

```js
function minCut(s) {
    const n = s.length;

    const dp = new Array(n).fill(0);

    const pal = Array.from(
        { length: n },
        () => new Array(n).fill(false)
    );

    for (let i = 0; i < n; i++) {

        dp[i] = i;

        for (let j = 0; j <= i; j++) {

            if (
                s[i] === s[j] &&
                (i - j <= 2 || pal[j + 1][i - 1])
            ) {

                pal[j][i] = true;

                if (j === 0) {
                    dp[i] = 0;
                } else {
                    dp[i] = Math.min(
                        dp[i],
                        dp[j - 1] + 1
                    );
                }
            }
        }
    }

    return dp[n - 1];
}
```

---

# Final Mental Model

---

# Prefix DP Recognition Formula

If problem says:

* "up to index i"
* "ending at i"
* "first i elements"
* "prefix"
* "build from left to right"
* "partition previous section"

then Prefix DP likely exists.

---

# DP State Evolution Path

| Level        | State Type                    |
| ------------ | ----------------------------- |
| Beginner     | `dp[i]`                       |
| Intermediate | `dp[i] + decisions`           |
| Advanced     | `dp[i][state]`                |
| Expert       | compressed / optimized states |

---

# Universal Prefix DP Framework

```js
const dp = [];

for (let i = 0; i < n; i++) {

    // examine previous states

    for (let j = 0; j < i; j++) {

        // transition
    }
}
```

---

# Hardest Skill in DP

Not coding.

The hardest part is:

1. defining state
2. defining transition
3. understanding what information must survive forward

That is the essence of dynamic programming.

---

# Recommended Progression Order

1. Climbing Stairs
2. House Robber
3. Decode Ways
4. Word Break
5. LIS
6. Arithmetic Subsequence
7. Palindrome Partitioning
8. Knapsack
9. Stock DP
10. Digit DP

That path gradually expands your DP state-design ability.
