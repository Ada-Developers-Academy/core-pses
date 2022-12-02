# Implement pairs_with_given_sum

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 6273b410
* title: PSE
* points: 3
### !question

Imagine working on software that processes lists of numbers. Create a function named `pairs_with_given_sum` It finds the number of pairs of `numbers` in a list which add up to a given `target`. This function should take in a list of whole `numbers` and a `target` as parameters. This function should have a return value of the integer of number of pairs.

| numbers                 | target | Number of pairs (return value)|
| ----------------------- | --- | --------------- |
| [1, 2, 4, 5]            | 6   | 2               |
| [97, 51, 49, 35, 3, 65] | 100 | 3               |

When considering example inputs and outputs, you likely considered edge cases. Your solution is only required to handle the nominal cases. As times allows, consider how to handle the edge cases you identified.

Sourced from: [Geeks for Geeks](https://www.geeksforgeeks.org/count-pairs-with-given-sum/)

### !end-question
### !placeholder

```python
def pairs_with_given_sum(numbers, target):
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_finds_two_pairs(self):
        # Arrange
        numbers = [1, 2, 4, 5]
        target = 6

        # Act
        result = pairs_with_given_sum(numbers, target)

        # Assert
        self.assertEqual(result, 2)

    def test_finds_three_pairs(self):
        # Arrange
        numbers = [97, 51, 49, 35, 3, 65]
        target = 100

        # Act
        result = pairs_with_given_sum(numbers, target)

        # Assert
        self.assertEqual(result, 3)
```
### !end-tests
### !explanation

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->



### !challenge

* type: short-answer
* id: eac1535f-27ee-43a3-9c43-fcb4732e64d4
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the time complexity of your solution? Explain. Define your variable(s) (i.e. `n` is the length of the list).

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
* id: ee2558a7-b6c3-4b1e-bd83-e901cd39f17b
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the space complexity of your solution? Explain. Define your variable(s) (i.e. `n` is the length of the list).

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge