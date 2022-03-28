# Instructor: kth Missing Positive Number

## O(n) Solution

```py
def kth_missing_positive_number(arr: List[int], k: int) -> int:
    # if the kth missing is less than arr[0]
    if k <= arr[0] - 1:
        return k
    k -= arr[0] - 1

    # search kth missing between the array numbers
    for i in range(len(arr) - 1):
        # missing between arr[i] and arr[i + 1]
        curr_missing = arr[i + 1] - arr[i] - 1
        # if the kth missing is between
        # arr[i] and arr[i + 1] -> return it
        if k <= curr_missing:
            return arr[i] + k
        # otherwise, proceed further
        k -= curr_missing

    # if the missing number if greater than arr[-1]
    return arr[-1] + k
```

## O(n log n) Solution with Binary Search

```py
    def kth_missing_positive_number(arr, k):
        left, right = 0, len(arr) - 1
        while left <= right:
            pivot = (left + right) // 2
            # If number of positive integers
            # which are missing before arr[pivot]
            # is less than k -->
            # continue to search on the right.
            if arr[pivot] - pivot - 1 < k:
                left = pivot + 1
            # Otherwise, go left.
            else:
                right = pivot - 1

        # At the end of the loop, left = right + 1,
        # and the kth missing is in-between arr[right] and arr[left].
        # The number of integers missing before arr[right] is
        # arr[right] - right - 1 -->
        # the number to return is
        # arr[right] + k - (arr[right] - right - 1) = k + left
        return left + k
```

[Source: Leetcode](https://leetcode.com/problems/kth-missing-positive-number/solution/)
