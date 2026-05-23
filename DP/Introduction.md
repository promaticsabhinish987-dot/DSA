## Dynamic Programming -> Reusing solved subproblems through stored state

Dynamic Programming is a method for designing algorithms. An algorithm designed with Dynamic Programming divides the problem into subproblems, finds solutions to the subproblems, and puts them together to form a complete solution to the problem we want to solve.


==> creating solusion by diving the current problem in to subproblems, and then combining them to get result.


```
Note  :- Reuse of previously computed subproblem results
- without reuse subprolem - its just a recursion, or a divide and conquere, just going down and up.
- DP is for ,
1. Overlapping subproblems
2. Repeated computation

DP eliminate the repeated work
If result already exist not recompute it, reuse it.
Note:-this storage is called memoization, cache
```

### Two Main DP Styles

1. Memoization (top bottom) --> recursion, cahe storage , cache to reuse the already computed value
2. Tabulation (bottom up) --> maintain a table


Core philosophy 

```
Future solution
depends on
previous solved states
```



### Actual Core Components

DP fundamentally requires TWO things:


#### 1. Overlapping Subproblems

Same smaller problem repeats. (same problem repeat, so we can compute it and store its result and whenever we encounter the same problem, we not recompute it we just use its stored result)

```
solve --> store --> use where required
```

#### 2. Optimal Substructure

Big solution can be built from smaller solutions. (we choose the optimal at each step)(and we build the solution one by one)

-> Optimal solution contian , optimal sub problems

#### 3. State Storage (Memoization/Tabulation)


#### What is the difference between recursion and dynamic programming


1. Normal recursion behaves like tree expention (it creates a tree)
2. DP compresses that tree into: Graph of reusable states (like once computer can point to the nodes where it needed in the future, cnabe one tomany) , many to many

#### What is the difference between Greedy and Dynamic programming

min no of coin to get garget

```
1,5,12,25
target = 36

// Greedy
chose bigestone

25 + 5 +5 +1 (4 coin) --> its optimizing in one direction only.

// dynamic programming

12+12+12 (3 coin) --> same ans with min coin

```


Note :- 
Greedy :- decision once maid, its final, no reconsideration.
DP :- stores many possible result(stores path not a variable or calculated value) --> “What if this path becomes better later?”
we keep track of optimal path, by computing all and considering the construction of a optimal path at each step.


Note :- create branches with all the possible ways , and get result from all, get and compare and return the optimal one.

#### Why we use backtracking in dp

#### 3 step solution

1. visualize
2. Find sub problem
3. Their relation -- help to combine them
4. generalize
5. example

## Patterns

1. Prefix DP
2. Sorted Prefix
3. Two sequence DP
4. Interval DP
5. Grid DP

NOte:- dp is solved with the grid visualization.
   




















