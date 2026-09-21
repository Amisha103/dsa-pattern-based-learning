# Two Sum

**LeetCode:** #1
**Difficulty:** Easy
**Topic:** Array
**Pattern:** Hashing → Complement Lookup
**Data Structure:** HashMap

## Approach

For every element, calculate:

`complement = target - current element`

* Check if the complement already exists in the `HashMap`.
* If it exists → return its index and the current index.
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

## Solution

```java
import java.util.*;

class Solution {
    public int[] twoSum(int[] arr, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < arr.length; i++) {
            int complement = target - arr[i];

            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }

            map.put(arr[i], i);
        }

        return new int[]{-1, -1};
    }
}
```
