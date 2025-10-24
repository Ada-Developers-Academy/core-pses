# Implement Tic Tac Toe

## Problem

Imagine working on software that determines the winner of a game of Tic Tac Toe. For more information on the rules of Tic Tac Toe, check out [the wiki here](https://en.wikipedia.org/wiki/Tic-tac-toe).

Create a function named `tic_tac_toe_winner` that is responsible for determing the state of a Tic Tac Toe board.
- This function should take in 3x3 matrix as a parameter
    - Each element is either an `'X'`, `'O'`, or empty string `''`
- This function should have a return value of:
    - The winner, `'X'` or `'O'`, if a winner exists
    - `'Tie'` for a full board with no winner
    - `None` for a game that is still in progress and has no winner

*Example 1:*
```
Input:
[
    ['X', 'O', 'X'],
    ['O', 'O', 'X'],
    ['X', 'X', 'O']
]

Output: 'Tie'
```

*Example 2:*
```
Input:
[
    ['X', 'O', 'X'],
    ['O', 'O', 'X'],
    ['X', 'O', '']
]

Output: 'O'
```

*Example 3:*
```
Input:
[
    ['X', 'O', 'O'],
    ['O', 'X', 'O'],
    ['', '', 'X']
]

Output: 'X'
```

*Example 4:*
```
Input:
[
    ['X', '', 'O'],
    ['O', 'X', 'X'],
    ['', '', '']
]

Output: None
```

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: 3b2bff25-f2ff-43ad-8531-95edf1affefc
* title: Code Solution
* points: 3
* topics: pse 10
##### !question

Code the solution to `tic_tac_toe_winner`

<details>
  <summary>Tests converted to Pytest</summary>

  ```python
    def test_tic_tac_toe_winner_no_winner_returns_tie():
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result == 'Tie'

    def test_tic_tac_toe_winner_incomplete_no_winner_returns_none():
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', '', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result is None

    def test_tic_tac_toe_winner_empty_board_returns_none():
        # Arrange
        board = [
            ['', '', ''],
            ['', '', ''],
            ['', '', '']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result is None

    def test_tic_tac_toe_winner_col_win_o():
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', 'O', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result == 'O'

    def test_tic_tac_toe_winner_row_win_x():
        # Arrange
        board =[
            ['O', 'O', 'X'],
            ['X', 'X', 'X'],
            ['O', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result == 'X'

    def test_tic_tac_toe_winner_diag_win_o():
        # Arrange
        board =[
            ['O', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result == 'O'
```

</details>

##### !end-question
##### !placeholder

```py
def tic_tac_toe_winner(board):
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
from main import tic_tac_toe_winner

class TestPython1(unittest.TestCase):
    def test_tic_tac_toe_winner_no_winner_returns_tie(self):
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, 'Tie')

    def test_tic_tac_toe_winner_incomplete_no_winner_returns_none(self):
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', '', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, None)

    def test_tic_tac_toe_winner_empty_board_returns_none(self):
        # Arrange
        board = [
            ['', '', ''],
            ['', '', ''],
            ['', '', '']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, None)

    def test_tic_tac_toe_winner_col_win_o(self):
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', 'O', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, 'O')

    def test_tic_tac_toe_winner_row_win_x(self):
        # Arrange
        board =[
            ['O', 'O', 'X'],
            ['X', 'X', 'X'],
            ['O', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, 'X')

    def test_tic_tac_toe_winner_diag_win_o(self):
        # Arrange
        board =[
            ['O', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, 'O')
```

##### !end-tests
##### !explanation

A solution:

```python
def tic_tac_toe_winner(board):
    # Check for row win
    # Ensure we do not consider 3 empty strings a win
    for row in range(3):
        if (board[row][0] == board[row][1] 
                and board[row][1] == board[row][2]
                and board[row][0] != ''):
            return board[row][0]

    # Check for column win
    for column in range(3):
        if (board[0][column] == board[1][column] 
                and board[1][column] == board[2][column]
                and board[0][column] != ''):
            return board[0][column]

    # Check for diagonal wins
    if (board[0][0] == board[1][1] 
            and board[1][1] == board[2][2]
            and board[0][0] != ''):
        return board[0][0]
    elif (board[0][2] == board[1][1] 
            and board[1][1] == board[2][0]
            and board[0][2] != ''):
        return board[0][2]

    # If none of these conditions match, check for game in progress
    for row in board:
        # If any space is '' --> Return None for 'game in progress'
        if '' in row:
            return None
    
    # If there is no winner and no open spaces, then the game is tied
    return 'Tie'
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 647d774c-443d-4c03-9e18-170c075289b4
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
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: fc625c83-dda0-43ba-a23f-252d97d0cc7b
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
<!-- prettier-ignore-end -->

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->