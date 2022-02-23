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

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 164a62ea-f936-4c6a-8b74-6d8248ba9c9d
* title: Ask Clarifying Questions
* topics: pse
##### !question

List five or more questions whose answers would clarify the problem statement

##### !end-question

##### !explanation 

Here are some example clarifying questions:

1. How should the function handle invalid user input (i.e. player_1 = ["lizards"](https://bigbangtheory.fandom.com/wiki/Rock,_Paper,_Scissors,_Lizard,_Spock))?
2. Should a user automatically lose if they have invalid input?
3. What should happen if both users have invalid input?
4. Does capitalization matter?
5. Does extra whitespace / punctuation matter?
6. Should anything be printed to the console?
7. Is the speed / memory usage of this function important?
8. Should there be a default value for each of the arguments?
 
##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->


<!-- Question 2 -->
<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: f4a31dc6-158a-4050-8a11-fead5fef0040
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `winner` for the nominal and edge cases you identified in the first step.

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

Example input/output and tests:

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
    assert result is None  
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 2bf3b413-e220-46aa-a99a-6c5f3d9715a9
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

##### !explanation
Example steps:

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

##### !end-explanation

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->

### !end-challenge

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: c3a9be9a-f946-4450-9b52-2fc6451a3111
* title: Implement Solution
### !question

Implement a solution to `winner` that implements the correct logic for the Rock, Paper, Scissors ruleset outlined above. 

Below is a selection of the unit tests.

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


### !end-question
### !placeholder

```python
def winner(player_1, player_2):
    pass
```
### !end-placeholder
### !tests
```python
import unittest
from main import *

class TestPython1(unittest.TestCase):
    def test_invalid_returns_none(self):
        # Arrange / Act
        result = winner("rock", "lizard")

        # Assert
        self.assertEqual(result,None)

    def test_rock_ties(self):
        # Arrange / Act
        result = winner("rock", "rock")

        # Assert
        self.assertEqual(result,"It's a tie!")

    def test_invalid_scissors_tie(self):
        # Arrange / Act
        result = winner("scissors", "scissors")

        # Assert
        self.assertEqual(result,"It's a tie!")

    def test_paper_ties(self):
        # Arrange / Act
        result = winner("paper", "paper")

        # Assert
        self.assertEqual(result,"It's a tie!")

    def test_player_1_rock_beats_scissors(self):
        # Arrange / Act
        result = winner("rock", "scissors")

        # Assert
        self.assertEqual(result, "Player 1 wins!")

    def test_player_2_rock_beats_scissors(self):
        # Arrange / Act
        result = winner("scissors","rock")

        # Assert
        self.assertEqual(result,"Player 2 wins!")

    def test_player_1_scissor_beats_paper(self):
        # Arrange / Act
        result = winner("scissors","paper")

        # Assert
        self.assertEqual(result, "Player 1 wins!")

    def test_player_2_scissors_beats_paper(self):
        # Arrange / Act
        result = winner("paper","scissors")

        # Assert
        self.assertEqual(result,"Player 2 wins!")

    def test_player_1_paper_beats_rock(self):
        # Arrange / Act
        result = winner("paper", "rock")

        # Assert
        self.assertEqual(result, "Player 1 wins!")

    def test_player_2_paper_beats_rock(self):
        # Arrange / Act
        result = winner("rock","paper")

        # Assert
        self.assertEqual(result,"Player 2 wins!")
```
### !end-tests
### !explanation

An example of a working implementation:

```python

VALID_MOVES = ["rock", "paper", "scissors"]

def winner(player_1, player_2):
    
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

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

