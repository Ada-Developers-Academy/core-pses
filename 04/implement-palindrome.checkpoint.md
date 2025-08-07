# Implement Palindrome

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 506644ae
* title: PSE
* points: 3
### !question

Imagine working on software that processes text. A palindrome is a word, phrase, or sequence that reads the same backward as forward.

Create a function named `check_palindrome` that determines if a string is a palindrome. This method should take in one string as a parameter. This method should return `True` if the string is a palindrome.

## Examples

| Example Input | Expected Output |
| ---------------------------- | ------------------- |
| `"Hello, world!"`            | `False`             |
| `"nascar"`                   | `False`             |
| `"racecar"`                  | `True`              |
| `"noon"`                     | `True`              |
| `"Mom"`                      | `True`              |
| `"Kayak"`                    | `True`              |

When considering example inputs and outputs, you likely considered edge cases. Your solution is only required to handle the nominal cases. As times allows, consider how to handle the edge cases you identified.

### !end-question
### !placeholder

```python
def check_palindrome(s):
    pass
```
### !end-placeholder


### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_check_palindrome_true_for_palindrome(self):
        # Arrange
        s = "kayak"

        # Act
        result = check_palindrome(s)

        # Assert
        self.assertEqual(result, True)

    def test_check_palindrome_false_if_not_palindrome(self):
        # Arrange
        s = "hello"

        # Act
        result = check_palindrome(s)

        # Assert
        self.assertEqual(result, False)
```
### !end-tests

### !end-challenge
<!-- prettier-ignore-end -->

### !challenge

* type: paragraph
* id: d9a44610-10a8-4a2e-9532-2cca7acd1c93
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the time complexity of your solution? Explain.

##### !end-question

##### !placeholder

Time Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

### !challenge

* type: paragraph
* id: e2d65d62-f902-454b-a780-81902fa8c9f9
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, Python, lists, matrices

##### !question

What is the space complexity of your solution? Explain.

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder
### !end-challenge