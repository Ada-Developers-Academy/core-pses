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
  def test_given_example_one(self):
      # Arrange
      list1 = [1, 2, 4, 5]
      list2 = [6]

      #  Act
      result = merge_lists(list1, list2)
      # Assert
      self.assertEqual([1, 2, 4, 5, 6], result)

  def test_given_example_two(self):
      # Arrange
      list1 = [-30, -10, 0, 15, 16]
      list2 = [-20, -5, 5]

      #  Act
      result = merge_lists(list1, list2)
      # Assert
      self.assertEqual([-30, -20, -10, -5, 0, 5, 15, 16], result)

  def test_list1_1_2_3_4_6_list2_5_7(self):
      # Arrange
      list1 = [1, 2, 3, 4, 6]
      list2 = [5, 7]

      #  Act
      result = merge_lists(list1, list2)
      # Assert
      self.assertEqual([1, 2, 3, 4, 5, 6, 7], result)
```

##### !end-tests

<!-- other optional sections -->
##### !hint 



##### !end-hint
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

### !end-challenge
<!-- prettier-ignore-end -->

### !challenge

* type: short-answer
* id: 0fbdbe91-696f-4de4-9f64-6d9a6d7d51fa
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the time complexity of your solution?

##### !end-question

##### !placeholder

Time Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

### !challenge

* type: short-answer
* id: 84041db2-d872-4058-9c95-1e1cfcef00d3
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the space complexity of your solution?

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge