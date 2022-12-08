# Instructor: Tic-Tac-Toe

It's important to note that all these solutions are O(1) for time and space complexity because a tic-tac-toe board doesn't grow.

## Solution with loops

```py
def tic_tac_toe_winner(board):
    '''
    INPUT: Tic Tac Toe board (3x3 matrix)
    OUTPUT: Winner
    '''
    # Determine if any column winners, eliminate 'win' of ''s
    for i in range(3):
        if (board[0][i] == board[1][i] == board[2][i]) and board[0][i] != '':
            return board[0][i]
    # Determine if any row winners, eliminate 'win' of ''s
    for i in range(3):
        if (board[i][0] == board[i][1] == board[i][2]) and board[i][0] != '':
            return board[i][0]
    # Determine if any diagonal winners, eliminate 'win' of ''s
    if (board[0][0] == board[1][1] == board[2][2]) and board[0][0] != '':
        return board[0][0]
    if (board[0][2] == board[1][1] == board[2][0]) and board[0][2] != '':
        return board[0][2]

    # If none of these conditions match, 
    for row in board:
        # If any space is '' --> Return None for 'game in progress'
        if '' in row:
            return None
    return 'Tie'
```

## With an Array of tuples

```py
def tic_tac_toe_winner(board):
    counter = 0
    for i in board:
        for element in i:
            if element !="":
                counter+=1
    
    combinations = [
      # horizontal
      ((0,0), (1,0), (2,0)),
      ((0,1), (1,1), (2,1)),
      ((0,2), (1,2), (2,2)),
      # vertical
      ((0,0), (0,1), (0,2)),
      ((1,0), (1,1), (1,2)),
      ((2,0), (2,1), (2,2)),
      # crossed
      ((0,0), (1,1), (2,2)),
      ((2,0), (1,1), (0,2))
    ]

    for coordinates in combinations:
        letters = [board[y][x] for x,y in coordinates]
        if len(set(letters)) == 1:
            return letters[0] # returns corresponding letter for winner (X/O)

    if counter==9:
        return "Tie"
    else:
        return None
```
