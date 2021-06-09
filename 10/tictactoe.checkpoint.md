# Tic Tac Toe

## Problem

Imagine working on software that determines the winner of a game of Tic Tac Toe. Create a function named `tictactoe` that is responsible for determing the state of a Tic Tac Toe board - Either there's no winner, it's a tie, `'X'` won, or `'O'` won. This function should take in 3x3 matrix as a parameter. Each element is either an `'X'`, `'O'`, or empty string `''`. This function should have a return value of the winner `'X'` or `'O'`, `'Tie'` (for a full board with no winner), or `None` (for a game that is still in progress).

*Example 1:*
Input:
```
[
    ['X', 'O', 'X'],
    ['O', 'O', 'X'],
    ['X', 'X', 'O']
]
```
Output: `'Tie'`

*Example 2:*
Input:
```
[
    ['X', 'O', 'X'],
    ['O', 'O', 'X'],
    ['X', 'O', '']
]
```
Output: `'O'`

*Example 3:*
Input:
```
[
    ['X', 'O', 'O'],
    ['O', 'X', 'O'],
    ['', '', 'X']
]
```
Output: `'X'`

*Example 4:*
Input:
```
[
    ['X', '', 'O'],
    ['O', 'X', 'X'],
    ['', '', '']
]
```
Output: `None`


## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 3d8275a0-d1ab-4189-be59-b228502b7ddf
* title: Ask Clarifying Questions
* points: 3
* topics: pse
##### !question

List five or more questions whose answers would clarify the problem statement

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation

Here are some example clarifying questions:
1. What consistutes a win for `'X'` or `'O'`?
1. What is a matrix with dimensions other than 3x3 is passed in?

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least five questions

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 6c0f79b1-ed10-4f12-b492-dbf003a293c5
* title: Consider Example Inputs and Outputs
* points: 3
* topics: pse
##### !question

List two or more sets of example arguments and the expected return value for these arguments

##### !end-question
##### !hint

Consider unexpected test cases and edge-case situations.

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint

##### !rubric

- The answer is wrong if there aren't at least two examples
- The answer is wrong if either of them aren't valid/consistent with each other
- The answer is wrong if the example inputs were not what the problem stated for valid input
- The answer is wrong if the example outputs were not what the problem stated or raised errors/exceptions

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 7a783007-7898-4d3f-815b-b989cb760a62
* title: Break Down the Problem into Sub-Problems
* points: 3
* topics: pse 10
##### !question

Divide the project prompt into two or more different sub-problems

##### !end-question
##### !hint

Consider:

- Any requirements around checking inputs
- Any requirements around calculations

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation

Here are some example sub-problems:

1. Check for valid input.
1. Determine if there is a win by in the column direction.
1. Determine if there is a win in the row direction.
1. Determine if there is a win in the diagonal direction.
1. Determine if there is a tie.

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least two sub-problems listed
- The answer is wrong if any of the sub-problems aren't relevant to the original problem

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 4 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: bb8d1391-b71a-4267-9fe8-88f2977917c4
* title: Create Logical Steps
* points: 3
* topics: pse 10
##### !question

Pick one of those problems from #3 and write a numbered list explaining how to solve that problem without using full lines of code

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !rubric

- The answer is wrong if it doesn't have at least two steps
- The answer is wrong if it isn't logical to another reader

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 5 -->
<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 3b2bff25-f2ff-43ad-8531-95edf1affefc
* title: Code Solution
* points: 3
* topics: pse 10
##### !question

Code the solution to Tic Tac Toe

<!-- prettier-ignore -->
<details>
  <summary>Tests converted to Pytest</summary>

  ```python

    def test_:

  ```
</details>

##### !end-question

##### !placeholder

```py
def tictactoe(board):
    '''
    INPUT: Tic Tac Toe board (3x3 matrix)
    OUTPUT: Winner
    '''
    pass
    
```

##### !end-placeholder

##### !tests

```py
import unittest
from main import knapsack

class TestPython1(unittest.TestCase):
    def test_
```

##### !end-tests

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation

A solution:

```python
```

##### !end-explanation

### !end-challenge

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.