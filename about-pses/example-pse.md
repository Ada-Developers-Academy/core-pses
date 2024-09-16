# Activity: Example PSE

## Problem Statement

Imagine working on software for a game of [Rock, Paper, Scissors](https://en.wikipedia.org/wiki/Rock_paper_scissors).

Create a function named `winner` that takes two arguments, the move for `player_1` and `player_2` (`"rock"`, `"paper"`, or `"scissors"`), and returns the winner (`"Player 1 wins!"`, `"Player 2 wins!"`, or `"It's a tie"`).

## Example Input/Output

| Input (Argument of the function) | Expected Output (Return value of the function) | Explanation|
|--|--|--|
|player_1 = `"rock"` <br> player_2 = `"scissors"`| `"Player 1 wins!"`|`"rock"` beats `"scissors"`|
|player_1 = `"rock"` <br> player_2 = `"rock"`| `"It's a tie!"`|`player_1` and `player_2` played the same move|

### Complete Rock, Paper, Scissors Rules
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

List three or more questions whose answers would clarify the problem statement. For each question, provide an answer which includes the effect your decision would have on how you would approach the problem.

##### !end-question

##### !explanation 

The following list provides some example clarifying questions, as well as what we might decide for ourselves is the answer. Several of these questions show examples of how we might think about the same issue in different ways. For example, questions 1, 2, and 3 are all about how to handle invalid input, but they each conceive of the problem slightly differently. Questions 4 and 5 are both getting at what variations in input would be considered valid or invalid. Questions 6 and 7 are about how to handle the possibility of extending the game to include more moves or more players. Notice that, even though we decide to stick with a more focused implementation for those questions, thinking through what some logical extensions might be (and in an interview context, bringing them up with the interviewer) can show that we're thinking about the problem in a broader context.

<br>

This prompt is pretty tightly specified, making it potentially more difficult to come up with clarifying questions. For future PSEs, there may be areas around edge cases, or sometimes even aspects of the core logic that may be more open to interpretation. Try to keep an eye out for areas of logic where it feels like you could make a decision about how to handle it, and then ask a question that would help you make that decision.

<br>

Try not to pose questions that are too specific to the implementation. For example, "Should I use a dictionary to store the winning combinations?" is too specific, and an interviewer is likely to leave choices about an implementation to us (and we should be prepared to justify our decisions). We should also avoid questions that change the observable behavior of a prompt. While we shouldn't ask about changing parameters or return values, or modifying behavior to something that conflicts with the prompt, we _could_ observe the requirements of the prompt, and mention how we might approach it if it were solely up to us. In an interview setting, this can give a sense of our thought process, and convey familiarity with the language over all, opening up space for a discussion. Ideally, we should think about questions that would help us understand the problem better and make decisions about how to approach it.

<br>

As stated, this list contains several questions that overlap in what they are asking as an example of different perspectives. Try not to include multiple questions about the same topic in your own questions. For example, if we ask about how to handle invalid input, we only need to ask once, not in three different ways as we have here, especially since the sample answers here are contradictory!

1. How should the function handle invalid user input (i.e. player_1 = "lizard")? The prompt doesn't specify how to handle invalid input, so I'll return `None`, which would allow the caller of my function to detect that there was an input I wasn't expecting. The caller could then decide how to handle that situation. This is also a convenient decision because, I'll only need to look for valid winning combinations, and if I don't find one, I can return `None`.
2. Should a user automatically lose if they have invalid input? I'll assume the input cannot be invalid. My function must be part of a larger system (something must be calling it!) and that system should handle input validation. This way, I can focus on the core logic of the scoring and not worry about input validation.
3. What should happen if both users have invalid input? While both players providing invalid input could be considered a tie, I don't want the function to act as though everything was fine if an input was invalid, so I'll return `None` if either player has invalid input. This way, the caller can detect that something went wrong and decide how to handle it. A drawback of this approach is that the caller can't tell _which_ input was invalid, only that one of them was.
4. Does capitalization matter? I'll assume that the input is case-insensitive, so I'll convert the input to lowercase before comparing it to the valid moves. This way, the caller can provide input in any case they like, and the function will still work. This could be helpful if this code was incorporated into a mobile platform where the device might auto-capitalize the first letter of a word.
5. Does extra whitespace / punctuation matter? I'll assume that my function is part of a larger game (something must be calling my function, right?) and that the caller will handle input validation. I will implement my logic looking only for the exact strings "rock", "paper", and "scissors". This way, the caller can handle any input validation they need to do, and I can focus on the core logic of the scoring.
6. I'm familiar with a variant of rock, paper, scissors that includes additional throws (lizard and Spock). Should I keep my approach focused on the basic rules, or should I use an implementation that could be extended to game variants? While I could write a helper function that accepts a data structure that encodes the valid moves and what beats what, I'll assume that I should focus on the basic rules for now. This way, I can get a working solution faster, and if I need to extend the game later, I can refactor my code to be more flexible.
7. When friends use rock, paper, scissors to make decisions, there are often more than two players. Should I keep my approach focused on the basic rules, or should I use an implementation that could be extended to support multiple players simultaneously? While I could write a helper function that accepts a list of moves made by all players, the multiplayer version introduces a few complications into resolving a round that I'd like to avoid for now. I'll assume that I should focus on the basic rules for now. This way, I can get a working solution faster, and if I need to extend the game later, I can refactor my code to be more flexible.

<br>

We should keep in mind that sometimes, areas of clarification may not jump out at us when we first read the prompt. It's completely OK to think through the prompt, and even start working on it. As we start to write code, we may realize that we need to ask a clarifying question. This is a normal part of the problem-solving process. So don't feel like we need to ask all our clarifying questions before we start working on the problem.

<br>

Even if we make a decision about how to handle a particular issue here, the unit tests may lead us to reconsider that decision. For example, if we decide to return `None` for invalid input, but the unit tests expect an error to be raised, we may need to change our implementation, but there's no need to come back and update the clarifying questions. The important thing is to think through the problem and make a decision based on the information we have at the time. When the tests differ from our initial thoughts, we can think of that as a case where the interviewer has given us new information that we need to incorporate into our solution.

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
    # ^rename with meaningful test name
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

The submission for this prompt only saves your input. The tests are not evaluated, nor is the syntax even checked. Please take care with your own syntax and how the tests are written, as _anything_ we submit will be marked "Correct."

<br>

Consider writing tests that capture decisions you made with your clarifying questions. For example, if you decided to return `None` for invalid input, you should write a test that checks that behavior. If you decided to return an error, you should write a test that checks for that error. If you decided to ignore invalid input, you should write a test that checks that the function works correctly with valid input.

<br>

Example input/output and tests:

```python
# example input 1: player_1 = "rock", player_2 = "scissors"
# expected output 1: "Player 1 wins!"

# example input 2: player_1 = "rock", player_2 = "lizards"
# expected output 2: None

# Note: This invalid input (player_2 = "lizards") might be better handled by raising an error, a topic covered during Unit 1.

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

Without writing code, describe how you would implement `winner` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

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

Implement a solution to `winner` that implements the correct logic for the Rock, Paper, Scissors rules outlined above. 

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

