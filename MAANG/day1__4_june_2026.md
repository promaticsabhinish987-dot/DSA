## MAANG DSA

They are testing pattern recognition under **constraints**.

### Why DSA even exist 

computers have limited resource like.

1. Time
2. Memory
3. CPU processing power
4. Network

DSA is the science of using those resource efficiently.


Note :- always think of 100M inputs , and think resource as money that you will give to them, and you have to find a way that will fulfil all their requirement in efficient way, with minimum cost.


### What they care about 

They evaluate candidate for these 5 steps every step matter the most.

```
1. Are you able to recognize the pattern in the given problem
2. are you able to choose the right data structure
3. are you able to choose the right algorithm
4. are you able to calculate the complexity
5. can you write code , implement it.


Question ---> signal --> find pattern ---> choose ds ---> choose algo ---> implement
```


Code is just a compressed form of your flow diagram.
Its a decoded form , and you cant directly think in it, so first you have to creare a flow diagram and then give a shape to it , encode it in compressed form with a language. 

### Pattern recognizatio --> every pattern save one resource efficiently and works for one thing very well , but sacrifice other resource.

Note :- there are only 15 to 20 pattern that cover most of the interview questions.


#### Pattern 1: Hashing

It can convert the time complexity from **O(n)sq to O(n)** , but take more space.
Hhen you need fast lookup , and you can sacrifice the space , use this.

Note :- it store key and value, so we can use it for

```
1. It does not store duplicate key ----> to detect the duplicate key
2. it can store the value which we can update -----> so we can increase and decrease the count to check the frequency of any element. whenever we encounter the same element, check it from tableand update its value by 1
3. It does not search linearly and if we know the key, we can get the and in O(1)  ----> so when you have key and you want to search use it for very fast lookup.
```


#### pattern 2 : Two poiner

Two pointer means we can point to the two element at a time and cn compare them. 
It work for two elements.
And sliding window also work for two pointers , but it also care about the intermediate element and it include and exclude based on requirement to scan a window of continuous element.


#### Pattern 3 : Sliding Window

Works on a range a window of element.


#### Pattern 4 : Binary search 

It works on sorted elements, where we can discard half of the element every time 

It convert the search time from O(n) to O(logN)

#### Pattern 5 : Stack


#### Pattern 6 : BFS

#### Pattern 7 : DFS

#### Pattern 8 : Heap 

Need top k frequently


#### Pattern 9 : Greedy

#### Pattern 10 : Dynamic Programming


# Solve questions from cluster not random






A complete MAANG-ready list of **~305 problems** would be very long. A more effective approach is to use a curated progression where each problem teaches a distinct pattern. Below is a high-signal list of the most commonly recommended LeetCode problems for interview preparation.

# Arrays (20)

| #  | Problem                                       |
| -- | --------------------------------------------- |
| 1  | 1. Two Sum                                    |
| 2  | 26. Remove Duplicates from Sorted Array       |
| 3  | 27. Remove Element                            |
| 4  | 53. Maximum Subarray                          |
| 5  | 66. Plus One                                  |
| 6  | 88. Merge Sorted Array                        |
| 7  | 118. Pascal's Triangle                        |
| 8  | 121. Best Time to Buy and Sell Stock          |
| 9  | 169. Majority Element                         |
| 10 | 189. Rotate Array                             |
| 11 | 217. Contains Duplicate                       |
| 12 | 238. Product of Array Except Self             |
| 13 | 268. Missing Number                           |
| 14 | 283. Move Zeroes                              |
| 15 | 414. Third Maximum Number                     |
| 16 | 448. Find All Numbers Disappeared in an Array |
| 17 | 485. Max Consecutive Ones                     |
| 18 | 724. Find Pivot Index                         |
| 19 | 1920. Build Array from Permutation            |
| 20 | 1929. Concatenation of Array                  |

---

# Hash Maps (20)

| #  | Problem                                  |
| -- | ---------------------------------------- |
| 1  | 1. Two Sum                               |
| 2  | 49. Group Anagrams                       |
| 3  | 128. Longest Consecutive Sequence        |
| 4  | 205. Isomorphic Strings                  |
| 5  | 217. Contains Duplicate                  |
| 6  | 219. Contains Duplicate II               |
| 7  | 242. Valid Anagram                       |
| 8  | 290. Word Pattern                        |
| 9  | 349. Intersection of Two Arrays          |
| 10 | 350. Intersection of Two Arrays II       |
| 11 | 387. First Unique Character in a String  |
| 12 | 389. Find the Difference                 |
| 13 | 451. Sort Characters by Frequency        |
| 14 | 560. Subarray Sum Equals K               |
| 15 | 594. Longest Harmonious Subsequence      |
| 16 | 692. Top K Frequent Words                |
| 17 | 771. Jewels and Stones                   |
| 18 | 1207. Unique Number of Occurrences       |
| 19 | 1657. Determine if Two Strings Are Close |
| 20 | 2364. Count Number of Bad Pairs          |

---

# Two Pointers (15)

| #  | Problem                          |
| -- | -------------------------------- |
| 1  | 125. Valid Palindrome            |
| 2  | 167. Two Sum II                  |
| 3  | 283. Move Zeroes                 |
| 4  | 344. Reverse String              |
| 5  | 345. Reverse Vowels              |
| 6  | 392. Is Subsequence              |
| 7  | 680. Valid Palindrome II         |
| 8  | 11. Container With Most Water    |
| 9  | 15. 3Sum                         |
| 10 | 42. Trapping Rain Water          |
| 11 | 75. Sort Colors                  |
| 12 | 88. Merge Sorted Array           |
| 13 | 977. Squares of a Sorted Array   |
| 14 | 881. Boats to Save People        |
| 15 | 986. Interval List Intersections |

---

# Sliding Window (20)

| #  | Problem                                           |
| -- | ------------------------------------------------- |
| 1  | 3. Longest Substring Without Repeating Characters |
| 2  | 76. Minimum Window Substring                      |
| 3  | 209. Minimum Size Subarray Sum                    |
| 4  | 239. Sliding Window Maximum                       |
| 5  | 424. Longest Repeating Character Replacement      |
| 6  | 438. Find All Anagrams in a String                |
| 7  | 567. Permutation in String                        |
| 8  | 643. Maximum Average Subarray I                   |
| 9  | 713. Subarray Product Less Than K                 |
| 10 | 904. Fruit Into Baskets                           |
| 11 | 930. Binary Subarrays With Sum                    |
| 12 | 1004. Max Consecutive Ones III                    |
| 13 | 1052. Grumpy Bookstore Owner                      |
| 14 | 1208. Get Equal Substrings Within Budget          |
| 15 | 1248. Count Number of Nice Subarrays              |
| 16 | 1343. Number of Subarrays of Size K               |
| 17 | 1456. Maximum Number of Vowels                    |
| 18 | 1493. Longest Subarray of 1's                     |
| 19 | 1838. Frequency of Most Frequent Element          |
| 20 | 2024. Maximize the Confusion of an Exam           |

---

# Binary Search (20)

| #  | Problem                                         |
| -- | ----------------------------------------------- |
| 1  | 35. Search Insert Position                      |
| 2  | 69. Sqrt(x)                                     |
| 3  | 74. Search a 2D Matrix                          |
| 4  | 153. Find Minimum in Rotated Sorted Array       |
| 5  | 162. Find Peak Element                          |
| 6  | 278. First Bad Version                          |
| 7  | 704. Binary Search                              |
| 8  | 875. Koko Eating Bananas                        |
| 9  | 981. Time Based Key Value Store                 |
| 10 | 1011. Capacity To Ship Packages                 |
| 11 | 33. Search in Rotated Sorted Array              |
| 12 | 34. Find First and Last Position                |
| 13 | 81. Search in Rotated Sorted Array II           |
| 14 | 222. Count Complete Tree Nodes                  |
| 15 | 378. Kth Smallest Element in a Sorted Matrix    |
| 16 | 410. Split Array Largest Sum                    |
| 17 | 540. Single Element in Sorted Array             |
| 18 | 658. Find K Closest Elements                    |
| 19 | 719. Find K-th Smallest Pair Distance           |
| 20 | 1482. Minimum Number of Days to Make m Bouquets |

---

# Stack (20)

| #  | Problem                                      |
| -- | -------------------------------------------- |
| 1  | 20. Valid Parentheses                        |
| 2  | 71. Simplify Path                            |
| 3  | 84. Largest Rectangle in Histogram           |
| 4  | 150. Evaluate Reverse Polish Notation        |
| 5  | 155. Min Stack                               |
| 6  | 225. Implement Stack using Queues            |
| 7  | 232. Implement Queue using Stacks            |
| 8  | 394. Decode String                           |
| 9  | 496. Next Greater Element I                  |
| 10 | 503. Next Greater Element II                 |
| 11 | 682. Baseball Game                           |
| 12 | 739. Daily Temperatures                      |
| 13 | 856. Score of Parentheses                    |
| 14 | 901. Online Stock Span                       |
| 15 | 946. Validate Stack Sequences                |
| 16 | 1047. Remove All Adjacent Duplicates         |
| 17 | 1190. Reverse Substrings Between Parentheses |
| 18 | 1475. Final Prices                           |
| 19 | 1544. Make The String Great                  |
| 20 | 2211. Count Collisions on a Road             |

---

# Linked List (20)

| #  | Problem                                |
| -- | -------------------------------------- |
| 1  | 21. Merge Two Sorted Lists             |
| 2  | 83. Remove Duplicates from Sorted List |
| 3  | 141. Linked List Cycle                 |
| 4  | 160. Intersection of Two Linked Lists  |
| 5  | 203. Remove Linked List Elements       |
| 6  | 206. Reverse Linked List               |
| 7  | 234. Palindrome Linked List            |
| 8  | 237. Delete Node in a Linked List      |
| 9  | 876. Middle of the Linked List         |
| 10 | 19. Remove Nth Node From End           |
| 11 | 24. Swap Nodes in Pairs                |
| 12 | 61. Rotate List                        |
| 13 | 92. Reverse Linked List II             |
| 14 | 138. Copy List with Random Pointer     |
| 15 | 142. Linked List Cycle II              |
| 16 | 143. Reorder List                      |
| 17 | 148. Sort List                         |
| 18 | 328. Odd Even Linked List              |
| 19 | 445. Add Two Numbers II                |
| 20 | 1721. Swapping Nodes in a Linked List  |

---

# Trees (40) — Must Do

* 94 Inorder Traversal
* 100 Same Tree
* 101 Symmetric Tree
* 104 Maximum Depth
* 110 Balanced Binary Tree
* 111 Minimum Depth
* 112 Path Sum
* 226 Invert Binary Tree
* 235 Lowest Common Ancestor BST
* 236 Lowest Common Ancestor Binary Tree
* 543 Diameter of Binary Tree
* 572 Subtree of Another Tree
* 617 Merge Two Binary Trees
* 700 Search in BST
* 701 Insert into BST
* 98 Validate BST
* 102 Level Order Traversal
* 103 Zigzag Level Order
* 107 Level Order Bottom
* 199 Right Side View
* 257 Binary Tree Paths
* 404 Sum of Left Leaves
* 437 Path Sum III
* 530 Minimum Absolute Difference BST
* 538 Convert BST to Greater Tree
* 653 Two Sum IV
* 863 All Nodes Distance K
* 987 Vertical Order Traversal
* 105 Construct Binary Tree
* 106 Construct Binary Tree II
* 114 Flatten Binary Tree
* 124 Binary Tree Maximum Path Sum
* 129 Sum Root to Leaf Numbers
* 173 BST Iterator
* 230 Kth Smallest BST
* 297 Serialize and Deserialize Binary Tree
* 450 Delete Node in BST
* 662 Maximum Width Binary Tree
* 1026 Maximum Difference Between Node and Ancestor
* 1448 Count Good Nodes

---

# Graphs (40) — Must Do

* 200 Number of Islands
* 695 Max Area of Island
* 733 Flood Fill
* 994 Rotting Oranges
* 133 Clone Graph
* 207 Course Schedule
* 210 Course Schedule II
* 547 Number of Provinces
* 841 Keys and Rooms
* 1091 Shortest Path in Binary Matrix
* 127 Word Ladder
* 399 Evaluate Division
* 417 Pacific Atlantic Water Flow
* 684 Redundant Connection
* 785 Is Graph Bipartite
* 802 Eventual Safe States
* 886 Possible Bipartition
* 909 Snakes and Ladders
* 1129 Shortest Path with Alternating Colors
* 1466 Reorder Routes
* 1514 Path with Maximum Probability
* 1584 Min Cost to Connect Points
* 1631 Path With Minimum Effort
* 1971 Find if Path Exists
* 743 Network Delay Time
* 787 Cheapest Flights Within K Stops
* 802 Eventual Safe States
* 1135 Connecting Cities With Minimum Cost
* 1192 Critical Connections
* 1319 Number of Operations to Make Network Connected
* 1376 Time Needed to Inform Employees
* 1557 Minimum Number of Vertices
* 1615 Maximal Network Rank
* 1786 Number of Restricted Paths
* 1857 Largest Color Value
* 1905 Count Sub Islands
* 1926 Nearest Exit
* 2101 Detonate the Maximum Bombs
* 2492 Minimum Score of a Path
* 2642 Design Graph With Shortest Path Calculator

---

# Heap (20)

* 215 Kth Largest Element
* 347 Top K Frequent Elements
* 373 Find K Pairs with Smallest Sums
* 378 Kth Smallest Element in Sorted Matrix
* 451 Sort Characters by Frequency
* 502 IPO
* 621 Task Scheduler
* 692 Top K Frequent Words
* 703 Kth Largest in Stream
* 767 Reorganize String
* 857 Minimum Cost to Hire K Workers
* 973 K Closest Points
* 1046 Last Stone Weight
* 1167 Minimum Cost to Connect Sticks
* 1642 Furthest Building
* 1801 Number of Orders in Backlog
* 1834 Single Threaded CPU
* 1962 Remove Stones
* 2233 Maximum Product After K Increments
* 2462 Total Cost to Hire Workers

---

# Greedy (20)

* 55 Jump Game
* 45 Jump Game II
* 134 Gas Station
* 435 Non-overlapping Intervals
* 452 Minimum Arrows
* 455 Assign Cookies
* 605 Can Place Flowers
* 646 Maximum Length of Pair Chain
* 649 Dota2 Senate
* 678 Valid Parenthesis String
* 714 Best Time Stock Fee
* 763 Partition Labels
* 860 Lemonade Change
* 1029 Two City Scheduling
* 1328 Break a Palindrome
* 135 Candy
* 1402 Reducing Dishes
* 1710 Maximum Units on a Truck
* 2279 Maximum Bags
* 2551 Put Marbles in Bags

---

# Dynamic Programming (50) — Most Important Category

Start with:

* 70 Climbing Stairs
* 746 Min Cost Climbing Stairs
* 198 House Robber
* 213 House Robber II
* 322 Coin Change
* 518 Coin Change II
* 300 Longest Increasing Subsequence
* 1143 Longest Common Subsequence
* 416 Partition Equal Subset Sum
* 494 Target Sum

Then continue with:

* 62 Unique Paths
* 63 Unique Paths II
* 64 Minimum Path Sum
* 91 Decode Ways
* 97 Interleaving String
* 120 Triangle
* 139 Word Break
* 152 Maximum Product Subarray
* 221 Maximal Square
* 279 Perfect Squares
* 309 Best Time to Buy and Sell Stock with Cooldown
* 337 House Robber III
* 343 Integer Break
* 377 Combination Sum IV
* 474 Ones and Zeroes
* 583 Delete Operation for Two Strings
* 647 Palindromic Substrings
* 673 Number of LIS
* 714 Stock with Transaction Fee
* 718 Maximum Length Repeated Subarray
* 740 Delete and Earn
* 931 Minimum Falling Path Sum
* 983 Minimum Cost For Tickets
* 1025 Divisor Game
* 1035 Uncrossed Lines
* 1043 Partition Array Maximum Sum
* 1137 N-th Tribonacci Number
* 1218 Longest Arithmetic Subsequence
* 1220 Count Vowel Permutation
* 1235 Maximum Profit in Job Scheduling
* 1312 Minimum Insertions Palindrome
* 1639 Number of Ways to Form Target String
* 1770 Maximum Score Multiplication Operations
* 1964 Longest Valid Obstacle Course
* 2140 Solving Questions With Brainpower
* 2328 Number of Increasing Paths
* 2466 Count Ways To Build Good Strings
* 5 Longest Palindromic Substring
* 72 Edit Distance

If you can solve **80–90%** of the problems above without looking at solutions, you're operating around the level expected for many software engineering interviews at companies such as Google, Meta, Amazon, and similar top-tier firms. The key is not the raw count; it's recognizing the pattern category within a few minutes and implementing it correctly under interview conditions.
































