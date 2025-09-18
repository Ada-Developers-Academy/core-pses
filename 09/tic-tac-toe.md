# Tic Tac Toe

Imagine working on software that determines the winner of a game of Tic Tac Toe. For more information on the rules of Tic Tac Toe, check out [the wiki here](https://en.wikipedia.org/wiki/Tic-tac-toe)

Create a function named `tic_tac_toe_winner` that is responsible for determing the state of a Tic Tac Toe board - Either no player has won yet, it's a tie, `'X'` won, or `'O'` won. 
- This function should take in 3x3 matrix as a parameter
    - Each element is either an `'X'`, `'O'`, or empty string `''`
- This function should have a return value of:
    - the winner `'X'` or `'O'` if a winner exists
    - `'Tie'` for a full board with no winner
    - `None` for a game that is still in progress and has no winner

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

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 7c868708-8d15-4d5f-a5e9-3301a62feaef
* title: Describe Your Understanding
* topics: pse
##### !question

Before you begin solving this problem, take a moment to think like a professional software engineer. 
- What do we know about the problem? 
- What assumptions can we make based on the information in the problem statement? 
- What further information do the example inputs and outputs give us?
- What questions would you ask a teammate, product manager, or interviewer to better understand the problem before writing any code?

<br>

In the box below, list 5 or more observations about the problem or questions whose answers would clarify the problem statement. For each observation or question, include information on why that observation is important or why you are asking the question.
- For each observation, answer how that observation will affect your approach to the problem.
- For each question, describe what you are hoping to clarify about the problem and provide an answer which includes the effect your decision would have on how you might approach the problem.

<br>

As you come up with observations and questions, assume that error handling for invalid data is managed outside the function. We want to focus on the core behavior of the function we will write. 

##### !end-question
##### !hint

Further questions to ask as you read through the problem statement and examples:
- What is the goal of the function?
- What are the types of the expected inputs and outputs?
- Are there any restrictions on any of the inputs?
  - For example: if any of the inputs are a list, do we know anything about how the list is ordered?
- What do the examples show us about the data types and values that are allowed for our inputs?
- What do the examples tell us about the return value in different scenarios?
- Reflecting on the observations you have made so far, what questions would give you new information?

<br>

Consider the following for inspiration:
- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Previous PSEs

##### !end-hint
##### !explanation

One of many possible responses could look like:

1. The problem statement says the input will be a 3x3 matrix. 
    - This means the input size will not change. While it's useful to think about how to handle any size board for practice, for this problem I can focus on a solution that only needs to account for looping over a 3x3 board.

2. Based on the examples, whether they are X or O, a winner needs to get 3 in a row, and this could be done vertically, horizontally, or diagonally. 
    - I can do something like hard code the indices of the matrix cells I need to check for each win location, or I can loop over the board in a few different ways to be able to check for a win condition.

3. Does the board need to be full for someone to win?
    - This would affect how we need to check the board for a win since we would need to check all cells, not just for 3 matching 'X' or 'O' in a row. 
    - This isn't explicitly described in the problem statment, but digging into the rules of tic tac toe, the game ends when the first person reaches 3 in a row, so there could be spots on the board that were not used.
    - This is supported by example 3 where there is a diagonal X win with empty spots left on the board, so I will assume that boards do not need to be full for there to be a winner.

4. What should the function return if two players have both won? For example: 3 Os across the top and 3 Xs across the bottom row?
    - This scenario isn't captured in the problem statement or examples. In a standard game of tic tac toe, there can only be one winner and the game ends when the first person reaches 3 in a row, so I will assume boards can only have one winner and I will return the first winner found on the board. 

5. Thinking about when we should return `None` or 'Tie' for a game still in progress, I only need to consider these states if a winner cannot be found. 
    - The problem statment says to return `None` "for a game that is still in progress and has no winner", and to return 'Tie' for a board with no winner and no places left to make moves. Both of these scenarios depend on there being no winner on the board, which I will only know if I check for winners first. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

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
def test_tic_tac_toe_winner_row_win_x():
    # nominal test case
    # Arrange
    board = [['X', 'X', 'X'],
             ['O', 'O', ''],
             ['', '', 'O']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result == 'X'

def test_tic_tac_toe_winner_empty_board_returns_none():
    # edge test case
    board = [['', '', ''],
             ['', '', ''],
             ['', '', '']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result is None

def test_tic_tac_toe_no_winner_returns_tie():
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
