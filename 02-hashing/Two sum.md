# Two Sum

**LeetCode:** #1
**Difficulty:** Easy
**Topic:** Array
**Pattern:** Hashing → Complement Lookup
**Data Structure:** HashMap

## Approach

For every element, calculate its complement:

`complement = target - current element`

* Check if the complement already exists in the `HashMap`.
* If it exists → return the stored index and current index.
* Otherwise, store the current element and its index.

## Why HashMap?

We need to quickly check whether the required complement has already appeared.

`HashMap` provides **O(1) average-time lookup**.

## Complexity

* **Time:** O(n) average
* **Space:** O(n)

## Key Takeaway

> **"What value do I need to reach the target, and have I seen it before?" → Think HashMap + Complement Lookup.**

**Pattern:** Complement Lookup
