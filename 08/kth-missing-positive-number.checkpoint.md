# Implement Find the Kth Missing Positive Number

Given an array `numbers` of positive integers sorted in a strictly increasing order and an integer `kth_missing`, find the positive integer at position `kth_missing` that is not present in the array.

**Example 1:**
```
Input: numbers = [2, 3, 4, 7, 11], kth_missing = 5
Output: 9

Explanation: 
- The missing positive integers are [1, 5, 6, 8, 9, 10, 12, 13, ...]
- The 5th missing positive integer is 9.

Missing numbers:    [1, 5, 6, 8, 9, 10, 12, 13,...]
Count:               1  2  3  4  5
```

**Example 2:**
```
Input: numbers = [1, 2, 3, 4], kth_missing = 2
Output: 6

Explanation: 
- The missing positive integers are [5, 6, 7, ...]. 
- The 2nd missing positive integer is 6.

Missing numbers:    [5, 6, 7, ...]
Count:               1  2
``` 

**Constraints:**
```
1 <= numbers[i]
1 <= kth_missing
numbers[i] < numbers[j] for 1 <= i < j <= numbers.length
```

Sourced from:  [Leetcode](https://leetcode.com/problems/kth-missing-positive-number/)

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 5a380194-96e2-4b87-9aa7-2fe407448e1f
* title: Find the Target Missing Positive Number
* points: 3
* topics: python, pse, python-lists
##### !question

Implement `find_missing_positive_number`. Use these tests to guide your solution.

<details>
  <summary>Tests converted to Pytest</summary>

  ```python
  def test_find_missing_positive_number_when_number_is_before_list():
      # Arrange
      numbers = [2, 3, 4, 7, 11]
      kth_missing = 1

      # Act
      result = find_missing_positive_number(numbers, kth_missing)

      # Assert
      assert result == 1

  def test_find_missing_number_finds_number_near_end_of_list():
      # Arrange
      numbers = [2, 3, 4, 7, 11]
      kth_missing = 5

      # Act
      result = find_missing_positive_number(numbers, kth_missing)
      
      # Assert
      assert result == 9

  def test_find_missing_positive_number_when_number_is_after_list():
      # Arrange
      numbers = [1, 2, 3, 4]
      kth_missing = 2

      # Act
      result = find_missing_positive_number(numbers, kth_missing)
      
      # Assert
      assert result == 6 

  def test_find_missing_positive_number_2nd_number_before_list_starts():
      # Arrange
      numbers = [3, 4, 5, 7, 11]
      kth_missing = 2

      # Act
      result = find_missing_positive_number(numbers, kth_missing)
      
      assert result == 2
  ```

</details>

##### !end-question
##### !placeholder

```python
def find_missing_positive_number(numbers, kth_missing):
    '''
    INPUTS: 
    - List of positive numbers in increasing order 
    - Positive integer `kth_missing`
    OUTPUT: The missing number at the kth_missing position
    '''

    pass
```

##### !end-placeholder

##### !tests

```py
import unittest
from main import find_missing_positive_number

class TestPython1(unittest.TestCase):
  def test_find_missing_positive_number_when_number_is_before_list(self):
    # Arrange
    numbers = [2, 3, 4, 7, 11]
    kth_missing = 1

    # Act
    result = find_missing_positive_number(numbers, kth_missing)

    # Assert
    self.assertEqual(1, result)

  def test_find_missing_number_finds_number_near_end_of_list(self):
      # Arrange
      numbers = [2, 3, 4, 7, 11]
      kth_missing = 5

      # Act
      result = find_missing_positive_number(numbers, kth_missing)
      
      # Assert
      self.assertEqual(9, result)

  def test_find_missing_positive_number_when_number_is_after_list(self):
      # Arrange
      numbers = [1, 2, 3, 4]
      kth_missing = 2

      # Act
      result = find_missing_positive_number(numbers, kth_missing)
      
      # Assert
      self.assertEqual(6, result)

  def test_find_missing_positive_number_2nd_number_before_list_starts(self):
      # Arrange
      numbers = [3, 4, 5, 7, 11]
      kth_missing = 2

      # Act
      result = find_missing_positive_number(numbers, kth_missing)
      
      self.assertEqual(2, result)

```

##### !end-tests
### !explanation

An example of an O(n) implementation:

```python
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

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 70178554-c412-45bb-80c9-1b10de5f75cb
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O
##### !question

What is the time complexity of your solution? Explain. Define your variable(s).

##### !end-question
##### !placeholder

Time Complexity?

##### !end-placeholder
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 143195b2-0991-4c74-9b81-88c2438e9f5f
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O
##### !question

What is the space complexity of your solution? Explain. Define your variable(s).

##### !end-question
##### !placeholder

Space Complexity?

##### !end-placeholder
### !end-challenge
<!-- prettier-ignore-end -->