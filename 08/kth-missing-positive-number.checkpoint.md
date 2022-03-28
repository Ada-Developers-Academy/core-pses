# PSE 8 - Kth Missing Positive Number

## Given this problem prompt

Given an array arr of positive integers sorted in a strictly increasing order, and an integer k.

Find the kth positive integer that is missing from this array.

**Example 1:**

```
Input: arr = [2,3,4,7,11], k = 5
Output: 9
Explanation: The missing positive integers are 
    [1,5,6,8,9,10,12,13,...]. 
    The 5th missing positive integer is 9.
```

**Example 2:**

```
Input: arr = [1,2,3,4], k = 2
Output: 6
Explanation: The missing positive integers are 
    [5,6,7,...]. The 2nd missing positive integer is 6.
``` 

**Constraints:**

```
1 <= arr.length <= 1000
1 <= arr[i] <= 1000
1 <= k <= 1000
arr[i] < arr[j] for 1 <= i < j <= arr.length
```

Sourced from:  [Leetcode](https://leetcode.com/problems/kth-missing-positive-number/)

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: code-snippet
* language: python3.6
* id: 5a380194-96e2-4b87-9aa7-2fe407448e1f
* title: Coding Solution
* points: 3
* topics: python, pse, python-lists

##### !question

Implement `kth_missing_positive_number`.  Use these tests to guide your solution.

<details>
  <summary>Tests converted to Pytest</summary>

  ```python
    def test_kth_missing_positive_number_finds_num_before_entire_given_list(self):
        # Arrange
        list = [2,3,4,7,11]
        k = 1

        # Act
        answer = kth_missing_positive_number(list, k)

        # Assert
        assert 1 == answer

    def test_kth_missing_number_finds_num_near_end_of_list(self):
        # Arrange
        list = [2,3,4,7,11]
        k = 5

        # Act
        answer = kth_missing_positive_number(list, k)
        
        # Assert
        assert 9 == answer

    def test_kth_missing_positive_number_finds_num_after_entire_given_list(self):
        # Arrange
        list = [1,2,3,4]
        k = 2

        # Act
        answer = kth_missing_positive_number(list, k)
        
        # Assert
        assert 6 == answer

    def test_kth_missing_positive_number_2nd_number_before_list_starts(self):
        # Arrange
        list = [3,4,5,7,11]
        k = 2

        # Act
        answer = kth_missing_positive_number(list, k)
        
        assert 2 == answer
  ```

</details>

##### !end-question

##### !placeholder

```python
def kth_missing_positive_number(numbers, k):
    '''
    INPUT: List of numbers in increating order & a positive integer k
    OUTPUT: The kth missing number
    '''

    pass
```

##### !end-placeholder

##### !tests

```py
import unittest
from main import kth_missing_positive_number

class TestPython1(unittest.TestCase):

  def test_kth_missing_positive_number_finds_num_after_entire_given_list(self):

    # Arrange
    list = [1,2,3,4]
    k = 2

    # Act
    answer = kth_missing_positive_number(list, k)

    # Assert
    self.assertEqual(6, answer)

  def test_kth_missing_number_finds_num_near_end_of_list(self):

    # Arrange
    list = [2,3,4,7,11]
    k = 5

    # Act
    answer = kth_missing_positive_number(list, k)

    # Assert
    self.assertEqual(9, answer)

  def test_kth_missing_positive_number_finds_num_before_entire_given_list(self):

    # Arrange
    list = [2,3,4,7,11]
    k = 1

    # Act
    answer = kth_missing_positive_number(list, k)

    # Assert
    self.assertEqual(1, answer)
    
```

##### !end-tests

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
