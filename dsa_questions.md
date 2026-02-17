# Linear Data Structures Questions (LeetCode Easy/Medium)

## 1. Arrays

### Q: Two Sum (LeetCode #1)

**Problem**: Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.
**Approach**:

- Use a Hash Map to store the difference (`target - num`) and its index.
- Iterate through the array; if the current number exists in the map, return the indices.
**Time Complexity**: O(n)

```python
def twoSum(nums, target):
    seen = {}
    for i, num in enumerate(nums):
        diff = target - num
        if diff in seen:
            return [seen[diff], i]
        seen[num] = i
```

### Q: Maximum Subarray (Kadane’s Algorithm)

**Problem**: Find the contiguous subarray which has the largest sum.
**Approach**:

- Maintain `current_sum` and `max_sum`.
- Add current element to `current_sum`. If `current_sum` becomes negative, reset it to 0. Update `max_sum` at each step.
**Time Complexity**: O(n)

---

## 2. Strings

### Q: Valid Anagram

**Problem**: Given two strings s and t, return true if t is an anagram of s.
**Approach**:

- Sort both strings and compare (O(n log n)).
- OR use a frequency counter (Hash Map or Array of size 26) to count characters (O(n)).

---

## 3. Linked List

### Q: Reverse Linked List

**Problem**: Reverse a singly linked list.
**Approach**:

- Use three pointers: `prev`, `curr`, `next`.
- Loop through the list, changing `curr.next` to `prev`, then move pointers forward.
**Time Complexity**: O(n)

```python
def reverseList(head):
    prev = None
    curr = head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev
```

### Q: Detect Cycle in a Linked List (Floyd’s Cycle Finding)

**Problem**: Determine if a linked list has a cycle.
**Approach**:

- Use two pointers, `slow` (moves 1 step) and `fast` (moves 2 steps).
- If they meet, there is a cycle. If `fast` reaches null, there is no cycle.

---

## 4. Stacks & Queues

### Q: Valid Parentheses

**Problem**: Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
**Approach**:

- Push opening brackets onto a stack.
- When a closing bracket is encountered, check if the stack is empty or if the top doesn't match.
- Finally, stack must be empty.

### Q: Implement Stack using Queues

**Problem**: Implement a LIFO stack using only two queues.
**Approach**:

- To `push(x)`: Add `x` to `q1`.
- To `pop()`: Move all elements except the last one from `q1` to `q2`. Return the last element. Swap names of `q1` and `q2`.
- (Optimized `push`: Add to `q2`, move all from `q1` to `q2`, swap `q1` and `q2` -> O(n) push, O(1) pop).
