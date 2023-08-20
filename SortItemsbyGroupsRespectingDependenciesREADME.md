# leet-day37

# Sort Items by Groups Respecting Dependencies

## Problem Description

You are given `n` items, each belonging to zero or one of `m` groups, where `group[i]` is the group that the `i-th` item belongs to, and it's equal to `-1` if the `i-th` item belongs to no group. The items and the groups are zero-indexed. A group can have no item belonging to it.

Your task is to return a sorted list of the items such that:

1. The items that belong to the same group are next to each other in the sorted list.
2. There are some relations between these items where `beforeItems[i]` is a list containing all the items that should come before the `i-th` item in the sorted array (to the left of the `i-th` item).

Return any valid solution if there is more than one solution, and return an empty list if there is no valid solution.

## Example

**Input:**
- `n = 8`
- `m = 2`
- `group = [-1,-1,1,0,0,1,0,-1]`
- `beforeItems = [[],[6],[5],[6],[3,6],[],[],[]]`

**Output:**
- `[6,3,4,1,5,2,0,7]`

**Explanation:**
- The `group` array indicates which group each item belongs to.
- The `beforeItems` array indicates the dependencies of each item.
- The items `[6,3,4,1,5,2,0,7]` satisfy the given conditions.

## Approach

1. Assign a group to each individual item that doesn't belong to any group.
2. Build dependency graphs for both groups and items using adjacency lists.
3. Perform topological sorting on the group graph and item graph.
4. For each group, sort the items within the group using the order obtained from the previous step.

## Complexity Analysis

- Time Complexity: The overall time complexity is O(n + m + n + m + n * log n + n * log n + n + n), which simplifies to O(n * log n), where `n` is the number of items and `m` is the number of groups.
- Space Complexity: O(n + n + m + m), which simplifies to O(n + m).
