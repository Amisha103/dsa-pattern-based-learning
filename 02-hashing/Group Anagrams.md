# Group Anagrams

**LeetCode:** #49
**Difficulty:** Medium
**Topic:** Array + String
**Pattern:** Hashing → Sorted String Signature
**Data Structure:** HashMap

## Approach

Anagrams have the same characters, so sorting the characters of each string produces the same key.

Example:

`eat → aet`
`tea → aet`
`ate → aet`

* Sort each string's characters.
* Use the sorted string as the `HashMap` key.
* Store all strings with the same key in the same list.
* Return all the grouped lists.

## Why HashMap?

All anagrams produce the same sorted string, which can be used as a unique **signature** to group them efficiently.

## Complexity

Let `n` = number of strings and `k` = maximum string length.

* **Time:** O(n × k log k)
* **Space:** O(n × k)

Sorting each string takes O(k log k).

## Key Takeaway

> **"How can I create the same signature for all anagrams?" → Sort each string and use the sorted string as a HashMap key.**

**Pattern:** Sorted String Signature

## Solution

```java
import java.util.*;

class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String, List<String>> map = new HashMap<>();

        for (String s : strs) {
            char[] chars = s.toCharArray();
            Arrays.sort(chars);

            String key = String.valueOf(chars);

            if (!map.containsKey(key)) {
                map.put(key, new ArrayList<>());
            }

            map.get(key).add(s);
        }

        return new ArrayList<>(map.values());
    }
}
```
