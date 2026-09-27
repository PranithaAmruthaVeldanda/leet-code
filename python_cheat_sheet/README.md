# 🐍 Python for LeetCode — Cheat Sheet

A quick reference for the Python syntax, data structures, and patterns I need while solving LeetCode / Blind 75 problems.

---

## 1. Variables & Math

```python
x = 10
x += 1
x -= 1
x *= 2
```

### Operators

```text
+       addition
-       subtraction
*       multiplication
/       division
//      integer division
%       remainder
**      power
```

```python
7 / 2     # 3.5
7 // 2    # 3
7 % 2     # 1
2 ** 3    # 8
```

### Useful functions

```python
len(nums)
sum(nums)
min(nums)
max(nums)
abs(x)
```

---

# 2. Lists

```python
nums = [1, 2, 3, 4]
```

### Access

```python
nums[0]       # first
nums[-1]      # last
```

### Modify

```python
nums.append(5)
nums.pop()
nums.remove(2)
```

### Slicing

```python
nums[1:3]     # index 1 through 2
nums[:3]      # first 3
nums[2:]      # from index 2
nums[::-1]    # reverse
```

### Sorting

```python
nums.sort()             # modifies nums
sorted_nums = sorted(nums)  # creates new list
```

```python
nums.sort(reverse=True)
```

### Remember

```text
List → ordered collection
Duplicates allowed
Index based
```

---

# 3. Loops ⭐

## Values only

Use when you only need the values:

```python
for num in nums:
    print(num)
```

Think:

> "Give me each value."

---
---
## Index + value

Use `enumerate()`:

```python
for i, num in enumerate(nums):
    print(i, num)
```

Think:

> "Give me the position AND the value."

Example:

```python
for i, num in enumerate(nums):
    if num == target:
        return i
```

---

## Index only

Use `range()`:

```python
for i in range(len(nums)):
    print(nums[i])
```

Use this when you need positions/neighbors:

```python
for i in range(len(nums) - 1):
    if nums[i] < nums[i + 1]:
        ...
```

---

## Range

```python
range(5)
# 0 1 2 3 4

range(1, 5)
# 1 2 3 4

range(5, 0, -1)
# 5 4 3 2 1
```

### Quick rule

```text
Value only
→ for num in nums

Index + value
→ for i, num in enumerate(nums)

Need positions/neighbors
→ for i in range(len(nums))
```

---

# 4. Strings

```python
s = "hello"
```

### Access

```python
s[0]
s[-1]
```

### Length

```python
len(s)
```

### Slice

```python
s[1:4]
```

### Reverse

```python
s[::-1]
```

### Check

```python
if "a" in s:
```

### Useful methods

```python
s.lower()
s.upper()
s.strip()
s.split()
```

Strings can be looped through:

```python
for char in s:
    ...
```

---

# 5. Dictionary / Hash Map ⭐⭐⭐

A dictionary stores:

```text
key → value
```

Create:

```python
result = {}
```

Store:

```python
result[num] = i
```

Get:

```python
result[num]
```

Check:

```python
if num in result:
```

Delete:

```python
del result[num]
```

---

## Frequency counting

```python
count = {}

for num in nums:
    if num in count:
        count[num] += 1
    else:
        count[num] = 1
```

Shorter:

```python
count[num] = count.get(num, 0) + 1
```

Remember:

```python
dictionary.get(key, default)
```

---

## Mental trigger

When you see:

> "Have I seen this?"

or:

> "I need to remember information about this value."

Think:

```text
HASH MAP / DICTIONARY
```

---

# 6. Set / Hash Set ⭐⭐⭐

A set stores unique values.

```python
seen = set()
```

Add:

```python
seen.add(num)
```

Check:

```python
if num in seen:
```

Remove:

```python
seen.remove(num)
```

Example:

```python
seen = set()

for num in nums:
    if num in seen:
        return True

    seen.add(num)

return False
```

### Mental trigger

> "Have I seen this before?"

→ **Set**

---

# 7. Dictionary vs Set

```text
Dictionary
    key → value

Set
    value only
```

### Use Dictionary when:

```text
number → index
character → count
word → information
```

### Use Set when:

```text
Have I seen this?
Is this value present?
Remove duplicates
```

---

# 8. Counter ⭐⭐

For frequency problems:

```python
from collections import Counter
```

```python
count = Counter(nums)
```

Example:

```python
nums = [1, 1, 2, 3, 3, 3]

Counter(nums)
```

Conceptually:

```text
1 → 2
2 → 1
3 → 3
```

For strings:

```python
count = Counter(s)
```

Useful for:

* Valid Anagram
* Top K Frequent Elements
* Frequency problems

---

# 9. defaultdict

```python
from collections import defaultdict
```

Example:

```python
groups = defaultdict(list)

groups["a"].append("apple")
groups["a"].append("ant")
```

Useful when one key maps to multiple values.

Common use:

```text
Group Anagrams
Graph adjacency lists
```

---

# 10. Stack ⭐⭐

Python list can be used as a stack.

```python
stack = []
```

Push:

```python
stack.append(x)
```

Pop:

```python
x = stack.pop()
```

Look at top:

```python
stack[-1]
```

Mental model:

```text
Last In → First Out

    3  ← top
    2
    1
```

Think **Stack** for:

* Parentheses
* Nested structures
* Undo-like behavior
* Monotonic stack problems

---

# 11. Queue / deque ⭐⭐

Use `deque`:

```python
from collections import deque
```

Create:

```python
queue = deque()
```

Add:

```python
queue.append(x)
```

Remove from front:

```python
x = queue.popleft()
```

Mental model:

```text
First In → First Out
```

Commonly used for:

```text
BFS
Tree level-order traversal
Graph traversal
```

---

# 12. Tuples

```python
pair = (2, 5)
```

Access:

```python
pair[0]
pair[1]
```

Very useful for:

```python
queue.append((row, col))
```

or:

```python
return [i, j]
```

Think:

```text
(row, col)
(x, y)
(i, j)
```

---

# 13. `if / elif / else`

```python
if x > 0:
    ...
elif x == 0:
    ...
else:
    ...
```

### Conditions

```python
x > 0
x < 0
x == 0
x != 0
x >= 0
x <= 0
```

### Logical operators

```python
and
or
not
```

Python:

```python
if x > 0 and y > 0:
```

Not:

```text
&&
||
!
```

---

# 14. `while` Loop ⭐

Useful for:

* Two pointers
* Binary search
* Linked lists

Example:

```python
left = 0
right = len(nums) - 1

while left < right:
    ...
```

---

# 15. `break`, `continue`, `return`

### break

Exit the loop:

```python
for num in nums:
    if num == target:
        break
```

### continue

Skip current iteration:

```python
for num in nums:
    if num < 0:
        continue
```

### return

Exit the entire function:

```python
if num == target:
    return True
```

Remember:

```text
break     → exit loop
continue  → skip iteration
return    → exit function
```

---

# 16. Two Pointers ⭐⭐⭐

Typical template:

```python
left = 0
right = len(nums) - 1

while left < right:

    if condition:
        left += 1
    else:
        right -= 1
```

Mental trigger:

```text
Sorted array
+
Pair / two ends
↓
Two Pointers
```

Common problems:

```text
Two Sum II
3Sum
Container With Most Water
Valid Palindrome
```

---

# 17. Sliding Window ⭐⭐⭐

Typical structure:

```python
left = 0

for right in range(len(nums)):

    # expand window

    while invalid:
        left += 1

    # use current window
```

Mental trigger:

```text
Contiguous section
+
Longest / shortest / maximum / minimum
↓
Sliding Window
```

Examples:

```text
Longest Substring Without Repeating Characters
Best Time to Buy and Sell Stock
Longest Repeating Character Replacement
```

---

# 18. Binary Search ⭐⭐⭐

Use when the search space is sorted or can be divided in half.

Template:

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

Mental trigger:

```text
Sorted
+
Can eliminate half
↓
Binary Search
```

Complexity:

```text
O(log n)
```

---

# 19. XOR ⭐⭐

Operator:

```python
a ^ b
```

Important properties:

```text
x ^ x = 0
x ^ 0 = x
```

Mental trigger:

> "Pairs cancel."

Useful for:

```text
Missing Number
Single Number
```

Example:

```python
result = 0

for num in nums:
    result ^= num

return result
```

---

# 20. Heap / Priority Queue ⭐⭐

```python
import heapq
```

Create:

```python
heap = []
```

Add:

```python
heapq.heappush(heap, x)
```

Remove smallest:

```python
x = heapq.heappop(heap)
```

Mental trigger:

```text
Top K
Repeatedly need smallest/largest
Priority
↓
Heap
```

Python `heapq` is a **min-heap** by default.

---

# 21. Linked Lists

Typical node:

```python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
```

Traverse:

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

Common patterns:

```text
Fast / slow pointers
Reverse linked list
Merge lists
```

---

# 22. Trees

Typical node:

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
```

DFS:

```python
def dfs(node):

    if not node:
        return

    dfs(node.left)
    dfs(node.right)
```

Remember:

```text
node.val
node.left
node.right
```

Mental trigger:

```text
Go deep → DFS
Level by level → BFS
```

---

# 23. List Comprehension

Useful Python shortcut:

```python
squares = [x * x for x in nums]
```

With condition:

```python
positive = [x for x in nums if x > 0]
```

Don't worry about mastering this immediately.

Normal loops are more important for learning algorithms.

---

# 24. Useful Built-ins

```python
len(nums)
sum(nums)
min(nums)
max(nums)
abs(x)
sorted(nums)
```

Check existence:

```python
x in nums
```

Reverse:

```python
nums[::-1]
```

---

# 25. Complexity Cheat Sheet

```text
O(1)       Constant
O(log n)   Binary Search
O(n)       One pass
O(n log n) Sorting
O(n²)      Nested loops
O(2ⁿ)      Backtracking (often)
```

Typical operations:

```text
Hash Set lookup       O(1) average
Hash Map lookup       O(1) average
List access nums[i]   O(1)
List search           O(n)
Sorting               O(n log n)
```

---

# 26. Pattern Recognition ⭐⭐⭐

This is more important than memorizing Python syntax.

| Problem clue                  | Think                   |
| ----------------------------- | ----------------------- |
| Have I seen this before?      | Hash Set                |
| Need value → information      | Hash Map                |
| Find pair that reaches target | Hash Map / Two Pointers |
| Count occurrences             | Dictionary / Counter    |
| Missing number                | Sum / XOR               |
| Pairs cancel                  | XOR                     |
| Sorted + pair                 | Two Pointers            |
| Contiguous + longest/shortest | Sliding Window          |
| Sorted + search               | Binary Search           |
| Matching / nested             | Stack                   |
| First in, first out           | Queue                   |
| Level by level                | BFS                     |
| Explore deeply                | DFS                     |
| Top K                         | Heap                    |
| Try every possible choice     | Backtracking            |
| Repeated subproblems          | Dynamic Programming     |

---

# 27. The Most Important Mental Questions

Before writing code, ask:

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

### 2. What have I already seen?

```text
Set?
Dictionary?
```

### 3. Do I need an index?

```text
No → for num in nums
Yes → enumerate(nums)
Need neighboring indexes → range()
```

### 4. Is the data sorted?

```text
Yes → Two Pointers / Binary Search
```

### 5. Is the answer about a contiguous section?

```text
Yes → Sliding Window
```

### 6. Is there nesting?

```text
Yes → Stack
```

### 7. Is it a tree/graph?

```text
Level by level → BFS
Go deep → DFS
```

---

# 28.1. Blind 75 Learning Order

Recommended progression:

```text
1. Two Sum
       ↓
2. Contains Duplicate
       ↓
3. Valid Anagram
       ↓
4. Missing Number
       ↓
5. Single Number
       ↓
6. 3Sum
       ↓
7. Valid Palindrome
       ↓
8. Best Time to Buy/Sell Stock
       ↓
9. Longest Substring Without Repeating Characters
       ↓
10. Binary Search
       ↓
11. Valid Parentheses
       ↓
12. Linked List problems
       ↓
13. Trees
       ↓
14. Graphs
       ↓
15. Heap
       ↓
16. Backtracking
       ↓
17. Dynamic Programming
```

---

# 🧠 Final Memory Map

```text
"I've seen this before?"
        ↓
      SET

"I need information about something I've seen?"
        ↓
     DICTIONARY

"Find a pair?"
        ↓
HASH MAP / TWO POINTERS

"Count things?"
        ↓
DICTIONARY / COUNTER

"Missing / pairs cancel?"
        ↓
   XOR / SUM

"Sorted?"
        ↓
TWO POINTERS / BINARY SEARCH

"Contiguous?"
        ↓
SLIDING WINDOW

"Nested / matching?"
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
```

## The 3 things to remember for every LeetCode problem

```text
1. PATTERN
   What type of problem is this?

2. DATA STRUCTURE
   What should I use?
   Set? Dict? Stack? Queue? Heap?

3. COMPLEXITY
   Time: ?
   Space: ?
```

**Don't try to memorize all of this at once.** Keep this README open while solving your first 10–20 problems. After you've used `dict`, `set`, `enumerate`, two pointers, sliding window, etc. several times, you'll start remembering them naturally.
