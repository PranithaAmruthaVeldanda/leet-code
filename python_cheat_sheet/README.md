# 🐍 Python DSA Cheat Sheet

A practical Python reference for solving **Data Structures & Algorithms (DSA)** and **LeetCode / Blind 75** problems.

---

# 📚 Table of Contents

* [Python Basics](#-python-basics)
* [Lists / Arrays](#-lists--arrays)
* [Strings](#-strings)
* [Hash Map / Dictionary](#-hash-map--dictionary)
* [Hash Set](#-hash-set)
* [Counter](#-counter)
* [Stack](#-stack)
* [Queue](#-queue)
* [Linked List](#-linked-list)
* [Trees](#-trees)
* [Graphs](#-graphs)
* [Two Pointers](#-two-pointers)
* [Sliding Window](#-sliding-window)
* [Binary Search](#-binary-search)
* [Prefix Sum](#-prefix-sum)
* [Heap / Priority Queue](#-heap--priority-queue)
* [Recursion](#-recursion)
* [Backtracking](#-backtracking)
* [Dynamic Programming](#-dynamic-programming)
* [Sorting](#-sorting)
* [XOR](#-xor)
* [Useful Python Functions](#-useful-python-functions)
* [Time & Space Complexity](#-time--space-complexity)
* [LeetCode Pattern Recognition](#-leetcode-pattern-recognition)

---

# 🐍 Python Basics

## Variables

```python
x = 10
name = "Python"
```

## Assignment vs Comparison

```python
x = 10       # assign

x == 10      # compare
x != 10      # not equal
```

## Comparison Operators

```python
a == b       # equal
a != b       # not equal
a > b        # greater
a < b        # smaller
a >= b       # greater or equal
a <= b       # smaller or equal
```

## Logical Operators

```python
and
or
not
```

Example:

```python
if x > 0 and y > 0:
    print("Both positive")
```

## Math Operators

```python
+       # addition
-       # subtraction
*       # multiplication
/       # division
//      # integer division
%       # remainder
**      # power
```

Example:

```python
7 / 2      # 3.5
7 // 2     # 3
7 % 2      # 1
2 ** 3     # 8
```

---

# 📦 Lists / Arrays

Python uses `list` for most array problems.

```python
nums = [1, 2, 3, 4]
```

## Access

```python
nums[0]       # first element
nums[-1]      # last element
nums[i]       # element at index i
```

## Modify

```python
nums.append(5)
nums.pop()
nums.insert(1, 10)
nums.remove(10)
```

## Slicing

```python
nums[1:4]     # index 1 to 3
nums[:3]      # first 3
nums[2:]      # index 2 onward
nums[::-1]    # reverse
```

## Loop Through Values

```python
for num in nums:
    print(num)
```

Use when you only need the value.

## Index + Value

```python
for i, num in enumerate(nums):
    print(i, num)
```

Use when you need both the index and value.

## Index

```python
for i in range(len(nums)):
    print(nums[i])
```

Use when you need indexes or neighboring elements.

### Remember

```text
Values only
→ for num in nums

Index + value
→ for i, num in enumerate(nums)

Indexes / neighbors
→ for i in range(len(nums))
```

## Sorting

```python
nums.sort()              # modifies nums

sorted_nums = sorted(nums)   # returns new list

nums.sort(reverse=True)
```

## List Complexity

| Operation        |   Complexity |
| ---------------- | -----------: |
| Access `nums[i]` |         O(1) |
| Search           |         O(n) |
| Append           | O(1) average |
| Pop from end     |         O(1) |
| Insert beginning |         O(n) |
| Delete beginning |         O(n) |
| Sort             |   O(n log n) |

---

# 🔤 Strings

```python
s = "hello"
```

## Access

```python
s[0]
s[-1]
```

## Length

```python
len(s)
```

## Slicing

```python
s[1:4]
s[:3]
s[2:]
s[::-1]       # reverse
```

## Check Character

```python
"a" in s
```

## Loop

```python
for char in s:
    print(char)
```

## Useful Methods

```python
s.lower()
s.upper()
s.strip()
s.split()
s.replace("a", "b")
```

---

# 🗂️ Hash Map / Dictionary

A dictionary stores:

```text
key → value
```

Create:

```python
hashmap = {}
```

## Add / Update

```python
hashmap[key] = value
```

## Access

```python
hashmap[key]
```

## Check

```python
if key in hashmap:
    ...
```

## Safe Access

```python
hashmap.get(key, 0)
```

## Delete

```python
del hashmap[key]
```

## Frequency Counting

```python
count = {}

for num in nums:
    count[num] = count.get(num, 0) + 1
```

Example:

```python
nums = [1, 2, 2, 3, 3, 3]

count = {}

for num in nums:
    count[num] = count.get(num, 0) + 1
```

Result:

```text
1 → 1
2 → 2
3 → 3
```

## Mental Trigger

```text
"Have I seen this?"
"Where did I see this?"
"What information belongs to this value?"
        ↓
    HASH MAP
```

## Complexity

Average:

```text
Insert → O(1)
Search → O(1)
Delete → O(1)
```

---

# 🔢 Hash Set

A set stores **unique values**.

```python
seen = set()
```

## Add

```python
seen.add(num)
```

## Check

```python
if num in seen:
    ...
```

## Remove

```python
seen.remove(num)
```

## Example

```python
seen = set()

for num in nums:

    if num in seen:
        return True

    seen.add(num)

return False
```

## Mental Trigger

```text
"Have I seen this before?"
        ↓
       SET
```

## Complexity

Average:

```text
Insert → O(1)
Search → O(1)
Delete → O(1)
```

---

# 🔢 Counter

`Counter` is a dictionary designed for counting.

```python
from collections import Counter
```

## Count Values

```python
nums = [1, 1, 2, 2, 2, 3]

count = Counter(nums)
```

Result:

```text
1 → 2
2 → 3
3 → 1
```

## Count Characters

```python
s = "banana"

count = Counter(s)
```

Result:

```text
a → 3
n → 2
b → 1
```

## Most Common

```python
count.most_common(2)
```

## Mental Trigger

```text
"How many times?"
"Frequency?"
"Most frequent?"
        ↓
     COUNTER
```

Common problems:

```text
Valid Anagram
Top K Frequent Elements
Frequency problems
```

---

# 📚 Stack

Python `list` can be used as a stack.

```python
stack = []
```

## Push

```python
stack.append(x)
```

## Pop

```python
x = stack.pop()
```

## Peek

```python
stack[-1]
```

Mental model:

```text
Last In → First Out

    3 ← top
    2
    1
```

## Mental Trigger

```text
Matching
Nested
Last In → First Out
        ↓
      STACK
```

Common problems:

```text
Valid Parentheses
Min Stack
Daily Temperatures
Evaluate Reverse Polish Notation
```

---

# 🚶 Queue

Use `deque` for a queue.

```python
from collections import deque

queue = deque()
```

## Add

```python
queue.append(x)
```

## Remove

```python
x = queue.popleft()
```

Mental model:

```text
First In → First Out

1 → 2 → 3 → 4
↑
front
```

## Mental Trigger

```text
First In → First Out
Level by level
        ↓
      QUEUE
```

Common use:

```text
BFS
Tree Level Order
Graph Traversal
```

---

# 🔗 Linked List

Typical LeetCode node:

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
```

## Traverse

```python
current = head

while current:
    print(current.val)
    current = current.next
```

Remember:

```text
node.val
node.next
```

## Common Patterns

```text
Fast / Slow Pointer
Reverse Linked List
Merge Linked Lists
Detect Cycle
```

---

# 🌳 Trees

Typical LeetCode node:

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
```

Remember:

```text
node.val
node.left
node.right
```

---

## DFS — Depth First Search

Go deep before exploring the next branch.

```python
def dfs(node):

    if not node:
        return

    dfs(node.left)
    dfs(node.right)
```

Mental trigger:

```text
"Go deep"
    ↓
   DFS
```

---

## BFS — Breadth First Search

Explore level by level.

```python
from collections import deque

queue = deque([root])

while queue:

    node = queue.popleft()

    if node.left:
        queue.append(node.left)

    if node.right:
        queue.append(node.right)
```

Mental trigger:

```text
"Level by level"
       ↓
      BFS
```

---

# 🕸️ Graphs

A common representation is an adjacency list.

```python
graph = {
    1: [2, 3],
    2: [1, 4],
    3: [1],
    4: [2]
}
```

Or:

```python
from collections import defaultdict

graph = defaultdict(list)

graph[a].append(b)
graph[b].append(a)
```

## Graph DFS

```python
def dfs(node):

    if node in visited:
        return

    visited.add(node)

    for neighbor in graph[node]:
        dfs(neighbor)
```

## Graph BFS

```python
queue = deque([start])
visited.add(start)

while queue:

    node = queue.popleft()

    for neighbor in graph[node]:

        if neighbor not in visited:
            visited.add(neighbor)
            queue.append(neighbor)
```

---

# ↔️ Two Pointers

Use two indexes that move through the data.

```python
left = 0
right = len(nums) - 1

while left < right:

    if nums[left] + nums[right] == target:
        return [left, right]

    elif nums[left] + nums[right] < target:
        left += 1

    else:
        right -= 1
```

## Mental Trigger

```text
SORTED
+
PAIR / TWO ENDS
        ↓
  TWO POINTERS
```

Common problems:

```text
Two Sum II
3Sum
Container With Most Water
Valid Palindrome
```

---

# 🪟 Sliding Window

Used for **contiguous** subarrays or substrings.

Basic template:

```python
left = 0

for right in range(len(nums)):

    # expand window

    while condition_is_invalid:
        left += 1

    # process window
```

Mental trigger:

```text
CONTIGUOUS
+
LONGEST / SHORTEST / MAX / MIN
        ↓
  SLIDING WINDOW
```

Common problems:

```text
Best Time to Buy and Sell Stock
Longest Substring Without Repeating Characters
Longest Repeating Character Replacement
Minimum Window Substring
```

---

# 🔎 Binary Search

Use when the search space is sorted or you can eliminate half the possibilities.

```python
left = 0
right = len(nums) - 1

while left <= right:

    mid = (left + right) // 2

    if nums[mid] == target:
        return mid

    elif nums[mid] < target:
        left = mid + 1

    else:
        right = mid - 1

return -1
```

Complexity:

```text
O(log n)
```

Mental trigger:

```text
SORTED
+
SEARCH
        ↓
 BINARY SEARCH
```

---

# ➕ Prefix Sum

Useful for repeated range/subarray sum calculations.

```python
prefix = [0]

for num in nums:
    prefix.append(prefix[-1] + num)
```

Example:

```text
nums:
[2, 4, 1, 5]

prefix:
[0, 2, 6, 7, 12]
```

Range sum from `i` to `j`:

```python
prefix[j + 1] - prefix[i]
```

Mental trigger:

```text
Repeated range / subarray sum
        ↓
    PREFIX SUM
```

---

# 🏆 Heap / Priority Queue

Python provides `heapq`.

```python
import heapq
```

## Create

```python
heap = []
```

## Add

```python
heapq.heappush(heap, x)
```

## Remove Smallest

```python
x = heapq.heappop(heap)
```

Python's `heapq` is a **min-heap** by default.

## Mental Trigger

```text
TOP K
+
PRIORITY
+
Repeatedly need smallest/largest
        ↓
       HEAP
```

Common problems:

```text
Kth Largest Element
Top K Frequent Elements
Merge K Sorted Lists
Find Median from Data Stream
```

---

# 🔁 Recursion

A function calls itself.

```python
def dfs(node):

    if not node:
        return

    dfs(node.left)
    dfs(node.right)
```

Every recursive solution needs:

### 1. Base Case

```python
if not node:
    return
```

### 2. Recursive Case

```python
dfs(node.left)
dfs(node.right)
```

Common use:

```text
Trees
Graphs
Backtracking
Divide and Conquer
```

---

# 🔙 Backtracking

Mental model:

```text
TRY
 ↓
EXPLORE
 ↓
UNDO
```

Template:

```python
def backtrack(path):

    if solution_found:
        result.append(path[:])
        return

    for choice in choices:

        path.append(choice)

        backtrack(path)

        path.pop()
```

The important part:

```python
path.pop()
```

This is the **undo** step.

Common problems:

```text
Subsets
Permutations
Combination Sum
Word Search
N-Queens
```

---

# 🧠 Dynamic Programming

Think:

> Solve smaller problems and reuse their answers.

Basic pattern:

```python
dp = [0] * (n + 1)

dp[0] = ...
dp[1] = ...

for i in range(2, n + 1):
    dp[i] = ...
```

Mental trigger:

```text
Repeated subproblems
+
Best answer / number of ways
        ↓
       DP
```

Common problems:

```text
Climbing Stairs
House Robber
Coin Change
Word Break
Longest Common Subsequence
```

---

# 🔃 Sorting

Python's built-in sorting is usually enough.

```python
nums.sort()
```

This modifies the original list.

```python
sorted_nums = sorted(nums)
```

This returns a new sorted list.

## Descending

```python
nums.sort(reverse=True)
```

## Sort by Key

```python
words.sort(key=len)
```

Complexity:

```text
O(n log n)
```

---

# ❌ XOR

XOR operator:

```python
a ^ b
```

Important properties:

```text
x ^ x = 0
x ^ 0 = x
```

Example:

```python
result = 0

for num in nums:
    result ^= num

return result
```

Mental trigger:

```text
PAIRS CANCEL
        ↓
       XOR
```

Common problems:

```text
Single Number
Missing Number
```

---

# 🛠️ Useful Python Functions

## Length

```python
len(nums)
```

## Sum

```python
sum(nums)
```

## Minimum

```python
min(nums)
```

## Maximum

```python
max(nums)
```

## Absolute Value

```python
abs(x)
```

## Sort

```python
sorted(nums)
```

## Check Membership

```python
x in nums
```

## Reverse

```python
nums[::-1]
```

---

# 📦 Important Imports

These are worth memorizing for LeetCode:

```python
from collections import Counter
from collections import defaultdict
from collections import deque

import heapq
```

---

# ⏱️ Time Complexity

| Complexity | Meaning         |
| ---------- | --------------- |
| O(1)       | Constant        |
| O(log n)   | Very fast       |
| O(n)       | One pass        |
| O(n log n) | Usually sorting |
| O(n²)      | Nested loops    |
| O(2ⁿ)      | Exponential     |
| O(n!)      | Very expensive  |

## Common Examples

```python
nums[i]
```

**O(1)**

```python
for num in nums:
```

**O(n)**

```python
for i in nums:
    for j in nums:
```

**O(n²)**

```python
nums.sort()
```

**O(n log n)**

---

# 🧩 LeetCode Pattern Recognition

| If the problem says / implies... | Think...                |
| -------------------------------- | ----------------------- |
| Have I seen this before?         | Set                     |
| Need value → information         | Hash Map                |
| Count occurrences                | Counter / Hash Map      |
| Find a pair                      | Hash Map / Two Pointers |
| Missing number                   | Sum / XOR               |
| Pairs cancel                     | XOR                     |
| Sorted + pair                    | Two Pointers            |
| Sorted + search                  | Binary Search           |
| Contiguous subarray              | Sliding Window          |
| Repeated range sum               | Prefix Sum              |
| Matching / nested                | Stack                   |
| First In → First Out             | Queue                   |
| Level by level                   | BFS                     |
| Go deep                          | DFS                     |
| Top K                            | Heap                    |
| Try every possibility            | Backtracking            |
| Repeated subproblems             | Dynamic Programming     |

---

# 🧠 The Most Important Mental Map

```text
┌──────────────────────────────────────────┐
│          LEETCODE PATTERN MAP            │
└──────────────────────────────────────────┘

"Have I seen this before?"
            ↓
           SET

"Need information about what I've seen?"
            ↓
        HASH MAP

"How many times?"
            ↓
         COUNTER

"Find a pair?"
            ↓
    HASH MAP / TWO POINTERS

"Sorted + pair?"
            ↓
      TWO POINTERS

"Sorted + search?"
            ↓
     BINARY SEARCH

"Contiguous + longest/shortest?"
            ↓
     SLIDING WINDOW

"Repeated range sum?"
            ↓
       PREFIX SUM

"Matching / nested?"
            ↓
          STACK

"Level by level?"
            ↓
           BFS

"Go deep?"
            ↓
           DFS

"Top K?"
            ↓
          HEAP

"Pairs cancel?"
            ↓
           XOR

"Try every possibility?"
            ↓
      BACKTRACKING

"Repeated subproblems?"
            ↓
           DP
```

---

# 🎯 Before Solving a LeetCode Problem

Ask these questions **before writing code**:

### 1. What am I looking for?

```text
Pair?
Duplicate?
Missing?
Count?
Longest?
Shortest?
Path?
```

### 2. What information do I need to remember?

```text
Set?
Dictionary?
Counter?
```

### 3. Do I need the index?

```text
No
→ for num in nums

Yes, index + value
→ enumerate(nums)

Need indexes / neighbors
→ range(len(nums))
```

### 4. Is the data sorted?

```text
Yes
→ Two Pointers / Binary Search
```

### 5. Is it asking about a contiguous section?

```text
Yes
→ Sliding Window / Prefix Sum
```

### 6. Is there nesting or matching?

```text
Yes
→ Stack
```

### 7. Is it a tree or graph?

```text
Go deep
→ DFS

Level by level
→ BFS
```

### 8. Do I need the top/bottom K?

```text
Yes
→ Heap
```

### 9. Are there repeated subproblems?

```text
Yes
→ Dynamic Programming
```

---

# 🚀 Quick LeetCode Templates

## Hash Map

```python
seen = {}

for i, num in enumerate(nums):

    if num in seen:
        ...

    seen[num] = i
```

## Hash Set

```python
seen = set()

for num in nums:

    if num in seen:
        ...

    seen.add(num)
```

## Two Pointers

```python
left = 0
right = len(nums) - 1

while left < right:

    ...

    left += 1
    right -= 1
```

## Sliding Window

```python
left = 0

for right in range(len(nums)):

    ...

    while condition:
        left += 1

    ...
```

## Binary Search

```python
left = 0
right = len(nums) - 1

while left <= right:

    mid = (left + right) // 2

    if nums[mid] == target:
        return mid

    elif nums[mid] < target:
        left = mid + 1

    else:
        right = mid - 1

return -1
```

## Stack

```python
stack = []

for x in nums:

    if condition:
        stack.append(x)
    else:
        stack.pop()
```

## BFS

```python
from collections import deque

queue = deque([start])
visited = set([start])

while queue:

    node = queue.popleft()

    for neighbor in graph[node]:

        if neighbor not in visited:
            visited.add(neighbor)
            queue.append(neighbor)
```

## DFS

```python
def dfs(node):

    if node in visited:
        return

    visited.add(node)

    for neighbor in graph[node]:
        dfs(neighbor)
```

---

# ⭐ My Core DSA Cheat Sheet

When stuck, start here:

```text
PAIR
→ Hash Map / Two Pointers

DUPLICATE
→ Set

COUNT
→ Counter / Dictionary

MISSING
→ Sum / XOR

SORTED
→ Two Pointers / Binary Search

CONTIGUOUS
→ Sliding Window / Prefix Sum

MATCHING
→ Stack

LEVELS
→ BFS

DEPTH / PATH
→ DFS

TOP K
→ Heap

ALL POSSIBILITIES
→ Backtracking

REPEATED SUBPROBLEMS
→ Dynamic Programming
```

---

# 📈 Recommended Learning Order

```text
Python Basics
      ↓
Lists & Strings
      ↓
Hash Map
      ↓
Hash Set
      ↓
Counter
      ↓
Two Pointers
      ↓
Sliding Window
      ↓
Stack
      ↓
Binary Search
      ↓
Linked Lists
      ↓
Trees
      ↓
Graphs
      ↓
Heap
      ↓
Backtracking
      ↓
Dynamic Programming
```

---

## 🏁 Goal

Don't try to memorize every solution.

Instead, learn to recognize:

```text
PROBLEM
   ↓
PATTERN
   ↓
DATA STRUCTURE
   ↓
ALGORITHM
   ↓
CODE
   ↓
TIME + SPACE COMPLEXITY
```

**The goal is not to memorize LeetCode solutions.
The goal is to recognize the pattern behind the problem.**
