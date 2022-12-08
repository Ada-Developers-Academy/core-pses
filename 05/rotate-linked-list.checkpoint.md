# Implement Rotate Linked List

<!-- prettier-ignore-start -->
### !challenge

* type: code-snippet
* language: python3.6
* id: 48651a9f-90c7-490a-90ab-0ef771f47170
* title: Rotate Linked List
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
# DO NOT MODIFY THE NODE CLASS
class Node:
    def __init__(self, value, next=None):
        self.value = value 
        # if next is None, this is the last element in the list
        self.next = next

    def __eq__(self, other):
        '''
        Understanding this function is NOT necessary for solving the problem;
        it is only used for the assertions.
        Feel free to explore your curiosity of how this works after the interview :)
        '''
        try:
            return (type(other) == Node and 
                    self.value == other.value and 
                    self.next == other.next)
        except RecursionError:
            raise Exception("Linked list has a cycle or is too large")

def rotate_list(head, k):
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
        lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
        expected = Node('e',  Node('a', Node('b', Node('c', Node('d')))))

        #  Act
        result = rotate_list(lst, 1)

        # Assert
        self.assertEqual(result, expected)

    def test_given_example_two(self):
        # Arrange
        lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
        expected = Node('d', Node('e', Node('a', Node('b', Node('c')))))

        #  Act
        result = rotate_list(lst, 2)

        # Assert
        self.assertEqual(result, expected)

    def test_given_example_three(self):
        # Arrange
        lst = Node('1', Node('2'))
        expected = Node('2', Node('1'))

        #  Act
        result = rotate_list(lst, 5)
        
        # Assert
        self.assertEqual(result, expected)

    def test_k_is_multiple_of_ll_length(self):
        # Arrange
        lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
        expected = Node('a', Node('b', Node('c', Node('d', Node('e')))))

        # Act
        result = rotate_list(lst, 10)

        # Assert
        self.assertEqual(result, expected)

    def test_k_is_zero(self):
        # Arrange
        lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
        expected = Node('a', Node('b', Node('c', Node('d', Node('e')))))

        # Act
        result = rotate_list(lst, 0)

        # Assert
        self.assertEqual(result, expected)

    def test_k_is_longer_than_ll_length(self):
        # Arrange
        lst = Node(55, Node(8, Node(2, Node(99))))
        expected = Node(2, Node(99, Node(55, Node(8))))
        
        # Act
        result = rotate_list(lst, 6)

        # Assert
        self.assertEqual(result, expected)
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

* type: paragraph
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

### !end-challenge

### !challenge

* type: paragraph
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

### !end-challenge