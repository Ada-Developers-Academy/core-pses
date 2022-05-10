# Tic Tac Toe

Imagine working on software that determines the winner of a game of Tic Tac Toe. Create a function named `tic_tac_toe_winner` that is responsible for determing the state of a Tic Tac Toe board - Either there's no winner, it's a tie, `'X'` won, or `'O'` won. This function should take in 3x3 matrix as a parameter. Each element is either an `'X'`, `'O'`, or empty string `''`. This function should have a return value of the winner `'X'` or `'O'`, `'Tie'` (for a full board with no winner), or `None` (for a game that is still in progress).

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
* id: 7c868708-8d15-4d5f-a5e9-3301a62feaef
* title: Ask Clarifying Questions
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation

Here are some example clarifying questions:

- What about if no one has won yet?
- What about if two players have both won for example 3: Os across the top and 3 Xs across the bottom row?
- Will the matrix always be 3x3?

##### !end-explanation
##### !rubric

- The answer is wrong if there aren't at least 3 questions

##### !end-rubric
### !end-challenge
<!-- prettier-ignore-end -->


<!-- Question 2 -->
<!-- prettier-ignore-start -->

### !challenge
* type: code-snippet
* language: python3.6
* id: 9333a730-4aa1-46f9-a7e3-764362539201
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `tic_tac_toe_winner` for the nominal and edge cases you identified in the first step.

*Note: Click the **Run Tests** button to save your tests for instructor feedback. No real tests are actually run again your unit tests.*

##### !end-question
##### !placeholder

```py
# example input 1:
# expected output 1:

# example input 2:
# expected output 2:

def test_nominal_case():
    # ^rename with meaningful test name
    # and complete test implementation below
    pass
    # arrange

    # act

    # assert

def test_edge_case():
    # ^rename with meaningful test name
    # and complete test implementation below
    pass
    
    # arrange
    
    # act
    
    # assert
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
def test_nominal_board():
    # nominal test case
    # Arrange
    board = [['X', 'X', 'X'],
             ['O', 'O', ''],
             ['', '', 'O']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result == 'X'

def test_empty_board():
    # edge test case
    board = [['', '', ''],
             ['', '', ''],
             ['', '', '']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result is None

def test_tied():
    # alternative test case
    # Arrange
    board = [['O', 'X', 'X'],
             ['X', 'O', 'O'],
             ['X', 'O', 'X']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result == 'Tie'
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: dfe2e816-9e1d-411d-84db-fd086fe82027
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `tic_tac_toe_winner` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n) solution:

1. Check for valid input
1. Create a list of all possible winning combinations
    * winning_combinations = [ [ (0, 0), (0, 1), (O, 2)],
                                 [(1, 0), (1, 1), (1, 2)],
                                 [(2, 0), (2, 1), (2, 2)],
                                 [ (0, 0), (1, 0), (2, 0)],
                                 [ (0, 1), (1, 1), (2, 1)],
                                 [ (0, 2), (1, 2), (2, 2)],
                                 [ (0, 0), (1, 1), (2, 2)],
                                 [ (0, 2), (1, 1), (2, 0)]
                    ]
1. Loop throught the winning combinations and check to see if each element in the conbination is equal and not empty.
    * If this is true return the value of the first element in the combination.

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
