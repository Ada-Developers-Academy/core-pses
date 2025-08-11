# Implement Merging Sorted Lists

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 0c1543ea-8274-4c5e-aa6b-cd7746bad763
* title: Merging Sorted Lists
* points: 3
* topics: python, lists, bigO
##### !question

Imagine working on software that processes lists of numbers. Create a function named `merge_lists` that takes two sorted lists and merges them into a single sorted list. This function should take in two lists of whole numbers. The function should return a new sorted list which consists of the elements of the two arguments.

| List 1                | List 2       | Output                            |
| --------------------- | ------------ | --------------------------------- |
| [1, 2, 4, 5]          | [6]          | [1, 2, 4, 5, 6]                   |
| [-30, -10, 0, 15, 16] | [-20, -5, 5] | [-30, -20, -10, -5, 0, 5, 15, 16] |

Sourced from: [Leetcode](https://leetcode.com/problems/merge-sorted-array/)

##### !end-question
##### !placeholder

```py
def merge_lists(list1, list2):
    pass
```

##### !end-placeholder
##### !tests

```py
import unittest
from main import *

class TestPython1(unittest.TestCase):
  def test_merge_lists_second_input_one_element(self):
      # Arrange
      list1 = [1, 2, 4, 5]
      list2 = [6]

      #  Act
      result = merge_lists(list1, list2)
      # Assert
      self.assertEqual([1, 2, 4, 5, 6], result)

  def test_merge_lists_multiple_interleaving_elements(self):
      # Arrange
      list1 = [-30, -10, 0, 15, 16]
      list2 = [-20, -5, 5]

      #  Act
      result = merge_lists(list1, list2)
      # Assert
      self.assertEqual([-30, -20, -10, -5, 0, 5, 15, 16], result)

  def test_merge_lists_first_list_smaller(self):
      # Arrange
      list1 = [5, 7]
      list2 = [1, 2, 3, 4, 6]

      #  Act
      result = merge_lists(list1, list2)
      # Assert
      self.assertEqual([1, 2, 3, 4, 5, 6, 7], result)
```

##### !end-tests
### !explanation

An example of an O(n) implementation:

```python
def merge_lists(list1, list2):
    pointer1 = 0
    pointer2 = 0
    result = []

    while pointer1 < len(list1) and pointer2 < len(list2):
        if list1[pointer1] < list2[pointer2]:
            result.append(list1[pointer1])
            pointer1 += 1
        else:
            result.append(list2[pointer2])
            pointer2 += 1

    while pointer1 < len(list1):
        result.append(list1[pointer1])
        pointer1 += 1

    while pointer2 < len(list2):
        result.append(list2[pointer2])
        pointer2 += 1
        
    return result
```

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 0fbdbe91-696f-4de4-9f64-6d9a6d7d51fa
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices
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
* id: 84041db2-d872-4058-9c95-1e1cfcef00d3
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices
##### !question

What is the space complexity of your solution? Explain. Define your variable(s).

##### !end-question
##### !placeholder

Space Complexity?

##### !end-placeholder
### !end-challenge
<!-- prettier-ignore-end -->
