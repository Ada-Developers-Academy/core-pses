# Tic Tac Toe

## Problem

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

        def test_tie(self):
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
    def test_incomplete(self):
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'X'],
            ['X', '', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result == None

    def test_col_win(self):
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

    def test_row_win(self):
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'O'],
            ['X', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        assert result == 'O'

    def test_diag_win(self):
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
    def test_tie(self):
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

    def test_incomplete(self):
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

    def test_col_win(self):
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

    def test_row_win(self):
        # Arrange
        board =[
            ['X', 'O', 'X'],
            ['O', 'O', 'O'],
            ['X', 'X', 'O']
        ]

        # Act
        result = tic_tac_toe_winner(board)

        # Assert
        self.assertEqual(result, 'O')

    def test_diag_win(self):
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


<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation

A solution:

```python
def tic_tac_toe_winner(board):

    # check for row win
    for i in range(3):
        if board[i][0] == board[i][1] and board[i][1] == board[i][2]:
            return board[i][0]

    # check for col win
    for j in range(3):
        if board[0][j] == board[1][j] and board[1][j] == board[2][j]:
            return board[0][j]

    # check for diag win
    if board[0][0] == board[1][1] and board[1][1] == board[2][2]:
        return board[0][0]
    elif board[0][2] == board[1][1] and board[1][1] == board[2][0]:
        return board[0][2]

    # check for tie or incomplete
    count = 0
    for row in board:
        for element in row:
            if element != '':
                count += 1
    
    if count == 9:
        return 'Tie'

    return None
```

##### !end-explanation

### !end-challenge

### !challenge

* type: short-answer
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

##### !answer

/.+/

##### !end-answer

### !end-challenge

### !challenge

* type: short-answer
* id: fc625c83-dda0-43ba-a23f-252d97d0cc7b
* title: What is the space complexity of your solution?
* points: 0
* topics: Big-O, Python, lists, matrices

##### !question

What is the space complexity of your solution?

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

