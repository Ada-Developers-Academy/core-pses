# Activity: Example PSE

## Problem Statement

Imagine working on software for a game of [Rock, Paper, Scissors](https://en.wikipedia.org/wiki/Rock_paper_scissors).

Create a function named `winner` that takes two arguments, the move for `player_1` and `player_2` (`"rock"`, `"paper"`, or `"scissors"`), and returns the winner (`"Player 1 wins!"`, `"Player 2 wins!"`, or `"It's a tie"`).

## Example Input/Output

| Input (Argument of the function) | Expected Output (Return value of the function) | Explanation|
|--|--|--|
|player_1 = `"rock"` <br> player_2 = `"scissors"`| `"Player 1 wins!"`|`"rock"` beats `"scissors"`|
|player_1 = `"rock"` <br> player_2 = `"rock"`| `"It's a tie!"`|`player_1` and `player_2` played the same move|

### Complete Rock, Paper, Scissors Ruleset
| input (first argument)| input (second argument) | output |
|--|--|--|
|**player_1** |**player_2**|**return value**|
|`"rock"`|`"rock"`|`"It's a tie!"`|
|`"paper"`|`"paper"`|`"It's a tie!"`|
|`"scissors"`|`"scissors"`|`"It's a tie!"`|
|`"rock"`|`"paper"`|`"Player 2 wins!"`|
|`"rock"`|`"scissors"`|`"Player 1 wins!"`|
|`"paper"`|`"rock"`|`"Player 1 wins!"`|
|`"paper"`|`"scissors"`|`"Player 2 wins!"`|
|`"scissors"`|`"rock"`|`"Player 2 wins!"`|
|`"scissors"`|`"paper"`|`"Player 1 wins!"`| 

## Prompts

### Ask Clarifying Questions

List five or more questions whose answers would clarify the problem statement.

```
1. How should the function handle invalid user input (i.e. player_1 = "lizards")?
2. 
3.
4.
5. 
```

### Write Unit Tests

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for get_highest_rated for the nominal and edge cases you identified in the first step.

```python
# example input 1: player_1 = "rock", player_2 = "scissors"
# expected output 1: "Player 1 wins!"

# example input 2: player_1 = "rock", player_2 = "lizards"
# expected output 2: None

# * Note: This invalid input (player_2 = "lizards") would be better handled by raising an exception, a topic covered during Unit 1.

def test_rock_beats_scissors():
    # arrange
    player_1 = "rock"
    player_2 = "scissors"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == "Player 1 wins!"

def test_invalid_input():
    # arrange
    player_1 = "rock"
    player_2 = "lizards"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == None  
```

### Create Logical Steps

Without writing code, describe how you would implement get_highest_rating in enough detail that someone else could write the code.

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere inbetween. What's important at this stage is to think through and outline the implementation before writing code.

```
1. Check if player_1 and player_2 are in ["rock", "paper", "scissors"]
    - If not, return None
2. Check for a tie: 
    - if player_1 == player_2, return "It's a tie!"
3. First deal with the case that player_1 == "rock"
    - if player_2 == "scissors", return "Player 1 wins!"
    - else (player_2 = "paper"), return "Player 2 wins!"
4. Next deal with the case that player_1 == "paper"
    - if player_2 == "rock", return "Player 1 wins!"
    - else (player_2 = "scissors"), return "Player 2 wins!"
5. Next deal with the case that player_1 == "scissors"
    - if player_2 == "rock", return "Player 2 wins!"
    - else (player_2 = "paper"), return "Player 1 wins!"

```

### Implement Solution

Implement a solution to `winner` that implements the correct logic for the Rock, Paper, Scissors ruleset outlined above. 

Below is a selection of the unit tests.

#### Tests
```python
def test_rock_beats_scissors():
    # arrange
    player_1 = "rock"
    player_2 = "scissors"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == "Player 1 wins!"

def test_invalid_input():
    # arrange
    player_1 = "rock"
    player_2 = "lizards"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result is None  
```

#### Solution
```python
VALID_MOVES = ["rock", "paper", "scissors"]

def winner(player_1, player_2)
    
    # invalid input
    if player_1 not in VALID_MOVES or player_2 not in VALID_MOVES:
        return None
    # tie
    if player_1 == player_2:
        return "It's a tie!"
    #  player 1 = rock
    elif player_1 == "rock":
        if player_2 == "scissors":
            return "Player 1 wins!"
        else:
            return "Player 2 wins!"
    # player 1 = paper
    elif player_1 == 'paper':
        if player_2 == 'rock':
            return "Player 1 wins!"
        else:
            return "Player 2 wins!"
    # player 1 = scissors
    elif player_1 == 'scissors':
        if player_2 == 'rock':
            return "Player 2 wins!"
        else:
            return "Player 1 wins!"
```