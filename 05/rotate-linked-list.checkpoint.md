# Implement Rotate Linked List

<!-- prettier-ignore-start -->
### !challenge

* type: code-snippet
* language: python3.6
* id: 48651a9f-90c7-490a-90ab-0ef771f47170
* title: Merging Sorted Lists
* points: 3
* topics: python, lists, bigO

##### !question

Imagine working on software that processes linked lists. Create a function named `rotate_list` that accepts a linked list and rotates it `k` places to the right. This function should take in the head of a linked list which has at least two nodes and a non-negative integer `k`. The function should return the head of the rotated list.

| List                  | k            | Output                            |
| --------------------- | ------------ | --------------------------------- |
| a -> b -> c -> d -> e | 1            | e -> a -> b -> c -> d
| a -> b -> c -> d -> e | 2            | d -> e -> a -> b -> c             |
| 1 -> 2                | 5            | 2 -> 1                            |

Sourced from: [Leetcode](https://leetcode.com/problems/rotate-list/)


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
* id: da542df1-77b0-401d-b5e4-e73549b69556
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the time complexity of your solution? Explain. Define your variable(s).

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
* id: e5552c1a-db8e-48ba-9ae9-1c91eedd20aa
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the space complexity of your solution? Explain. Define your variable(s).

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge