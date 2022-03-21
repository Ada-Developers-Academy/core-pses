# Implement pairs_with_given_sums

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 6273b410
* title: PSE
* points: 3
### !question

Imagine ...

### !end-question
### !placeholder

```python
def pairs_with_given_sums(numbers, target):
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
        result = pairs_with_given_sums(numbers, target)

        # Assert
        self.assertEqual(result, 2)

    def test_finds_three_pairs(self):
        # Arrange
        numbers = [97, 51, 49, 35, 3, 65]
        target = 100

        # Act
        result = pairs_with_given_sums(numbers, target)

        # Assert
        self.assertEqual(result, 3)
```
### !end-tests
### !explanation

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->


