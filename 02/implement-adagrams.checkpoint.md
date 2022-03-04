# Implement Adagrams

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: f998bb4d
* title: PSE
* points: 3
### !question

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

| Input       | Expected Output |
| ----------- | --------------- |
| `"DOG"`     | `5`             |
| `"CAT"`     | `5`             |
| `"CABBAGE"` | `14`            |
| `"QUARTY"`  | `24`            |
| `""`        | `0`             |
| `"Dog"`     | `5`             |
| `"DOG"`     | `5`             |
| `"dOG"`     | `5`             |
| `"dOG!@)"`     | `5`             |

### !end-question
### !placeholder

```python
def score():
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestChallenge(unittest.TestCase):
    def test_scores_words(self):
        self.assertEqual(score("DOG"), 5)
        self.assertEqual(score("CAT"), 5)
        self.assertEqual(score("CABBAGE"), 14)
        self.assertEqual(score("QUARTZ"), 24)
        self.assertEqual(score(""), 0)
        self.assertEqual(score("Dog"), 5)
        self.assertEqual(score("DOG"), 5)
        self.assertEqual(score("dOG"), 5)
        self.assertEqual(score("dOG!@)"), 5)
```
### !end-tests
### !explanation

An example of a working implementation:

```python
def score(word):
    total_score = 0
    for character in word:
        letter = character.upper()
        if letter in "AEIOULNRST":
            total_score += 1
        elif letter in "DG":
            total_score += 2
        elif letter in "BCMP":
            total_score += 3
        elif letter in "FHVWY":
            total_score += 4
        elif letter in "K":
            total_score += 5
        elif letter in "JX":
            total_score += 8
        elif letter in "QZ":
            total_score += 10

    return total_score
```

Another example of a working implementation:

```python
def score(word):
    scores = {
        "A": 1, "E": 1, "I": 1, "O": 1, "U": 1, "L": 1, "N": 1, "R": 1, "S": 1, "T": 1, "D": 2, "G": 2, "B": 3, "C": 3, "M": 3, "P": 3, "F": 4, "H": 4, "V": 4, "W": 4, "Y": 4, "K": 5, "J": 8, "X": 8, "Q": 10, "Z": 10
    }
    total_score = 0
    for letter in word:
        if letter.upper() in scores:
            total_score += scores[letter.upper()]

    return total_score
```

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 085ad8a1-7dbd-49ad-aa7a-2213dd0d3c76
* title: Create Logical Steps
* topics: pse

##### !question

Without writing code, describe how you would implement `get_highest_rating` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere inbetween. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation
### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

