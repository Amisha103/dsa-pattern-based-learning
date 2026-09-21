# 217. Contains Duplicate

**LeetCode:** [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
**Difficulty:** Easy
**Topic:** Array
**Pattern:** Hashing → Membership Check
**Data Structure:** HashSet

## Approach

We need to check whether an element has appeared before.

* Traverse the array.
* If the current element already exists in the `HashSet` → duplicate found → return `true`.
* Otherwise, add it to the set.
* If the traversal finishes → return `false`.

### Why HashSet?

We only need to know **whether a value exists**, not its index or frequency.

##  Java

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> set = new HashSet<>();

        for (int i = 0; i < nums.length; i++) {
            if (set.contains(nums[i])) {
                return true;
            }
            set.add(nums[i]);
        }

        return false;
    }
}
```

## Complexity

* **Time:** O(n) average
* **Space:** O(n)

## Key Takeaway

> **"Have I seen this element before?" → Think HashSet.**

**Pattern:** Membership Check
