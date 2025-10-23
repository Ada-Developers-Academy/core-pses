# Instructor: Find the Kth Missing Positive Number

## O(n) Solution

```py
def find_missing_positive_number(numbers, kth_missing):
    # if the kth_missing is less than numbers[0]
    if kth_missing <= numbers[0] - 1:
        return kth_missing
    kth_missing -= numbers[0] - 1

    # search for kth_missing between the array numbers
    for i in range(len(numbers) - 1):
        # missing between numbers[i] and numbers[i + 1]
        curr_missing = numbers[i + 1] - numbers[i] - 1
        # if the kth_missing is between
        # numbers[i] and numbers[i + 1] -> return it
        if kth_missing <= curr_missing:
            return numbers[i] + kth_missing
        # otherwise, proceed further
        kth_missing -= curr_missing

    # if the missing number if greater than numbers[-1]
    return numbers[-1] + kth_missing
```

## O(n log n) Solution with Binary Search

```py
    def find_missing_positive_number(numbers, kth_missing):
        left, right = 0, len(numbers) - 1
        while left <= right:
            pivot = (left + right) // 2
            # If number of positive integers
            # which are missing before numbers[pivot]
            # is less than kth_missing -->
            # continue to search on the right.
            if numbers[pivot] - pivot - 1 < kth_missing:
                left = pivot + 1
            # Otherwise, go left.
            else:
                right = pivot - 1

        # At the end of the loop, left = right + 1,
        # and the kth_missing is in-between numbers[right] and numbers[left].
        # The number of integers missing before numbers[right] is
        # numbers[right] - right - 1 -->
        # the number to return is
        # numbers[right] + kth_missing - (numbers[right] - right - 1) = kth_missing + left
        return left + kth_missing
```

[Source: Leetcode](https://leetcode.com/problems/kth-missing-positive-number/solution/)
