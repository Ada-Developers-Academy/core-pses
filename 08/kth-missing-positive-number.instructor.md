# Instructor: Find the Missing Positive Number

## O(n) Solution

```py
def find_missing_positive_number(numbers, missing_target):
    # if the missing_target is less than numbers[0]
    if missing_target <= numbers[0] - 1:
        return missing_target
    missing_target -= numbers[0] - 1

    # search for missing_target between the array numbers
    for i in range(len(numbers) - 1):
        # missing between numbers[i] and numbers[i + 1]
        curr_missing = numbers[i + 1] - numbers[i] - 1
        # if the missing_target is between
        # numbers[i] and numbers[i + 1] -> return it
        if missing_target <= curr_missing:
            return numbers[i] + missing_target
        # otherwise, proceed further
        missing_target -= curr_missing

    # if the missing number if greater than numbers[-1]
    return numbers[-1] + missing_target
```

## O(n log n) Solution with Binary Search

```py
    def find_missing_positive_number(numbers, missing_target):
        left, right = 0, len(numbers) - 1
        while left <= right:
            pivot = (left + right) // 2
            # If number of positive integers
            # which are missing before numbers[pivot]
            # is less than missing_target -->
            # continue to search on the right.
            if numbers[pivot] - pivot - 1 < missing_target:
                left = pivot + 1
            # Otherwise, go left.
            else:
                right = pivot - 1

        # At the end of the loop, left = right + 1,
        # and the missing_target is in-between numbers[right] and numbers[left].
        # The number of integers missing before numbers[right] is
        # numbers[right] - right - 1 -->
        # the number to return is
        # numbers[right] + missing_target - (numbers[right] - right - 1) = missing_target + left
        return left + missing_target
```

[Source: Leetcode](https://leetcode.com/problems/kth-missing-positive-number/solution/)
