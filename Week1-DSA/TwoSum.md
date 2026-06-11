# Two Sum

## What I Learned

Two Sum is a problem where I need to find two numbers whose sum equals the target value.

Example:

```java
nums = [2,7,11,15]
target = 9
```

Output:

```java
[0,1]
```

because:

```java
2 + 7 = 9
```

---

## First Thought

Check every pair.

```java
for each number
    check every other number
```

This works but is slow.

Time Complexity:

```java
O(n²)
```

---

## Better Approach

Use a HashMap.

Store:

```java
number -> index
```

While traversing the array:

1. Find the required number

```java
diff = target - currentNumber
```

2. Check if diff already exists in HashMap

3. If yes, return the indices

4. Otherwise store current number

---

## Code

```java
public class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> prevMap = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int num = nums[i];
            int diff = target - num;

            if (prevMap.containsKey(diff)) {
                return new int[] { prevMap.get(diff), i };
            }

            prevMap.put(num, i);
        }

        return new int[] {};
    }
}
```

---

## Concepts Used

* Array Traversal
* HashMap
* Key-Value Pair
* Lookup Optimization

---

## Complexity

Time Complexity:

```java
O(n)
```

Space Complexity:

```java
O(n)
```

---

## My Takeaway

This problem taught me how HashMap can reduce a brute-force O(n²) solution to O(n).

Whenever I need fast searching while traversing an array, I should think about using HashMap.
