# leet-day80

# Number of Good Pairs

## Problem Description

Given an array of integers `nums`, you need to return the number of good pairs.

A pair `(i, j)` is called good if `nums[i] == nums[j]` and `i < j`.

### Example

**Input**:
```
nums = [1,2,3,1,1,3]
```

**Output**:
```
4
```

**Explanation**:
There are 4 good pairs `(0,3)`, `(0,4)`, `(3,4)`, `(2,5)` (0-indexed).

### Constraints

- `1 <= nums.length <= 100`
- `1 <= nums[i] <= 100`

## Approach

We can use a hash map to count the occurrences of each number in the array. For each number that appears `n` times, we can form `n * (n - 1) / 2` good pairs.

## Algorithm

1. Initialize an empty hash map `count` to store the count of each number.
2. Initialize a variable `goodPairs` to 0 to keep track of the total number of good pairs.
3. Iterate through the `nums` array:
   - For each number `num`, check if it's already in the `count` map.
     - If it's in the map, increment its count and add `(count[num] - 1)` to `goodPairs`. This accounts for the good pairs that can be formed with the new occurrence.
     - If it's not in the map, initialize its count to 1.
4. After iterating through the entire array, `goodPairs` will contain the total number of good pairs.
5. Return `goodPairs` as the result.

## Complexity Analysis

- Time complexity: O(n), where n is the length of the `nums` array. We iterate through the array once to count the occurrences.
- Space complexity: O(n) in the worst case if all elements are unique and need to be stored in the `count` map.

