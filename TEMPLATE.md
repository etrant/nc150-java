# Two Sum

## Problem Essence
Find two numbers in an array that add up to a target sum.

## Intuition Building
1. Naive approach: check all pairs (inefficient)
2. Key insight: complement of each number is what we're looking for
3. Hash table can give O(1) lookup for complements

## Approach
1. Create a hash map to store numbers and their indices
2. Iterate through the array:
   a. Calculate the complement (target - current number)
   b. If complement exists in hash map, return its index and current index
   c. If not, add current number and its index to hash map
3. If no solution found, return an empty array or throw an exception

## Code Skeleton
```python
def twoSum(nums, target):
    num_map = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i
    return []  # or raise an exception
```

## Complexity
- Time: O(n) - single pass through the array
- Space: O(n) - hash map can store up to n elements

## Lessons Learned
- Hash tables can transform many O(n^2) problems into O(n) solutions
- Trading space for time is a common optimization technique

## Improvement Ideas
- For sorted arrays, two-pointer technique could solve in O(n) time and O(1) space
- Consider handling edge cases (empty array, no solution) more explicitly
