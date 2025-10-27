# Instructor: Find the Kth Missing Positive Number

## O(n) Solution

```py
def find_kth_missing_positive_number(numbers, kth_missing):
    # if numbers is empty, the kth missing value is kth_missing itself
    if not numbers:
        return kth_missing

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
def find_kth_missing_positive_number(numbers, kth_missing):
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

```py
def find_kth_missing_positive_number(numbers, kth_missing):
    lo = 0
    hi = len(numbers)  # exclusive
    
    # find the lowest index where the number of missing values >= kth_missing
    while lo < hi:
        # due to truncate, mid will always be < hi (at least lo)
        # this means mid is always in the array bounds
        mid = (lo + hi) // 2
  
        # number we expect to find at any position (if there are no missing numbers)
        # is just the index + 1 (since we start at 1)
        # the difference between what we expect and what we have is how many are
        # missing up to that point (prior to the mid index)
        num_missing = numbers[mid] - (mid + 1)
  
        # we are looking for the smallest index where the number of missing values
        # exceeds or is equal to kth_missing
        # finding that position means that we've found the index where we move
        # from having too few missing numbers to having too many or just enough,
        # so the value itself must be "between" the found location and the one before it
        if num_missing < kth_missing:
            lo = mid + 1  # too few, so shift range up
        else:
            hi = mid  # too many or still tied, so shift range down
            
      return lo + kth_missing

    # lo is now the index of the first position where the number of missing
    # values is >= kth_missing
    # our general formula to find the number of missing values at any index
    # is numbers[index] - (index + 1)
    # we can use this to find the number of missing values at the previous index
    # which tells us how many more we need to count up to reach kth_missing.
    # the index before lo is lo-1, so:
    # num_missing_before = numbers[lo - 1] - (lo - 1 + 1)
    #   = numbers[lo - 1] - lo (distribute the - and simplify)
    # This would fail if lo is 0, but we'll see this works out in the end
    # The number of missing values we still need to count up to reach kth_missing is:
    # remaining_missing = kth_missing - num_missing_before
    #   = kth_missing - (numbers[lo - 1] - lo) (substitute)
    #   = kth_missing - numbers[lo - 1] + lo (distribute)
    #   = kth_missing + lo - numbers[lo - 1] (rearrange)
    # This means the target missing number is the remaining missing beyond the last
    # number we have, which is
    # target_missing = numbers[lo - 1] + remaining_missing
    #   = numbers[lo - 1] + kth_missing + lo - numbers[lo - 1] (substitute)
    #   = numbers[lo - 1] - numbers[lo - 1] + kth_missing + lo (rearrange)
    #   = kth_missing + lo (simplify)
    # Notice that if lo is 0, this still works, since the expression that would
    # fail (numbers[lo - 1]) is eliminated in the simplification.
    # Though this result may be surprising, we can verify it manually. For example,
    # for an empty list, lo will be 0, and the target missing number will always
    # be kth_missing, which is correct.
    # We can try this with cases where the target missing comes before the first
    # number in the list, between numbers in the list, and after the last number
    # in the list (with and without missing numbers in the list), and it always works.
    # This is a case where a relatively simple looking result is not obvious
    # until you work through the reasoning.
```

[Source: Leetcode](https://leetcode.com/problems/kth-missing-positive-number/solution/)
