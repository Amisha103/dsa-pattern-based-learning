# Valid Anagram

**LeetCode:** #242
**Difficulty:** Easy
**Topic:** String
**Pattern:** Hashing → Frequency Counting
**Data Structure:** Frequency Array

## Approach

Count the frequency of each character in `s`.

* Increment the count for every character in `s`.
* Traverse `t` and decrement the corresponding count.
* If a character's count is already `0`, `t` contains that character more times → return `false`.
* Finally, check that all frequencies are `0`.

Since the strings contain only lowercase English letters, an array of size `26` is sufficient.

## Why Frequency Array?

There are only **26 possible lowercase English letters**, so we can directly store their frequencies using an integer array instead of a `HashMap`.

## Complexity

* **Time:** O(n)
* **Space:** O(1) — fixed array of size 26

## Key Takeaway

> **"Do the two strings contain the same characters with the same frequencies?" → Think Frequency Counting.**

**Pattern:** Frequency Counting

## Solution

```java
class Solution {
    public boolean isAnagram(String s, String t) {

        if (s.length() != t.length()) {
            return false;
        }

        int[] arr = new int[26];

        for (char c : s.toCharArray()) {
            arr[c - 'a']++;
        }

        for (char c : t.toCharArray()) {
            if (arr[c - 'a'] > 0) {
                arr[c - 'a']--;
            } else {
                return false;
            }
        }

        for (int i = 0; i < 26; i++) {
            if (arr[i] != 0) {
                return false;
            }
        }

        return true;
    }
}
```

## Follow-up: Unicode

For Unicode characters, we cannot use a fixed array of size `26`.

Use a `HashMap<Character, Integer>` (or a Unicode-aware code-point approach) to store character frequencies.
