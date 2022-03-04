# Adagrams

## Problem Statement

Imagine programming the logic for a word game.

In this game, every player submits one word. Each word gets a score based on the letters in the word and its point value.

Create a function named `score` that is responsible for scoring a given word.

This function should take in a string named `word` as a parameter. This function should return the word's total number of points.

Refer to this table for the point values of each letter.

| Letter                       | Value |
| ---------------------------- | ----- |
| A, E, I, O, U, L, N, R, S, T | 1     |
| D, G                         | 2     |
| B, C, M, P                   | 3     |
| F, H, V, W, Y                | 4     |
| K                            | 5     |
| J, X                         | 8     |
| Q, Z                         | 10    |

### Examples

| Input                                              | Expected Output |
| -------------------------------------------------- | --------------- |
| `"DOG"`                                            | `5`             |
| `"CAT"`                                            | `5`             |
| `"CABBAGE"`                                        | `14`            |
| [`"QUARTZ"`](https://en.wikipedia.org/wiki/Quartz) | `24`            |

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 87058b56-6678-4ef9-b1e0-c3ebddeb4bf9
* title: Ask Clarifying Questions
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Previous PSEs

##### !end-hint
##### !explanation 

Here are some example clarifying questions:

1. How should the function handle special characters?
1. Should the function be case in sensitive?
1. How should the function handle an empty string?
 
##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 890d7045-28cb-4832-812b-d65803ce2618
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `score` for the nominal and edge cases you identified in the first step.

*Note: Click the **Run Tests** button to save your tests for instructor feedback. No real tests are actually run again your unit tests.*
##### !end-question

##### !placeholder

```py
# example input 1:
# expected output 1:

# example input 2:
# expected output 2:

def test_nominal_case():
    # ^rename with meaninful test name
    # and complete test implementation below
    pass
    # arrange

    # act

    # assert

def test_edge_case():
    pass
```

##### !end-placeholder

##### !tests

```py
import unittest

class TestPython1(unittest.TestCase):
  def test_always_pass(self):
    self.assertEqual(1,1)
```

##### !end-tests
##### !explanation 

Example tests:

```python
def test_correct_score_for_all_letters():
    # Arrange
    word = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'

    # Act
    result = score(word)

    # Assert
    assert result == 87

def test_case_insensitive():
    # Arrange
    word = 'dOg'

    # Act
    result = score(word)

    # Assert
    assert result == 5

def test_ignores_special_characters():
    def test_case_insensitive():
    # Arrange
    word = 'dOg!@)'

    # Act
    result = score(word)

    # Assert
    assert result == 5

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

