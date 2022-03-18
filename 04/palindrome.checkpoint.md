# Palindrome

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 911f2970
* title: PSE
* points: 3
### !question

Imagine working on software that processes text. A palindrome is a word, phrase, or sequence that reads the same backward as forward.

Create a function named `is_palindrome` that determines if a string is a palindrome. This method should take in one string as a parameter. This method should return `True` if the string is a palindrome.

## Examples

| Original string as parameter | Is it a palindrome? |
| ---------------------------- | ------------------- |
| `"Hello, world!"`            | No                  |
| `"racecar"`                  | Yes                 |
| `"noon"`                     | Yes                 |
| `"mom"`                      | Yes                 |
| `"kayak"`                    | Yes                 |

### !end-question
### !placeholder

```python
def palindrome(s):
    pass
```
### !end-placeholder


### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_true_for_palindrome(self):
        # Arrange
        s = "kayak"

        # Act
        result = palindrome(s)

        # Assert
        assert result == True

    def test_false_for_not_palindrome(self):
        # Arrange
        s = "hello"

        # Act
        result = palindrome(s)

        # Assert
        assert result == False
```
### !end-tests

### !end-challenge
<!-- prettier-ignore-end -->