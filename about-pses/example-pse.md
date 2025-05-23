# Activity: Example PSE

## Problem Statement

Imagine working on software for a game of [Rock, Paper, Scissors](https://en.wikipedia.org/wiki/Rock_paper_scissors).

Create a function named `winner` that takes two arguments, the move for `player_1` and `player_2` (`"rock"`, `"paper"`, or `"scissors"`), and returns the winner (`"Player 1 wins!"`, `"Player 2 wins!"`, or `"It's a tie"`).

## Example Input/Output

| Input (Argument of the function) | Expected Output (Return value of the function) | Explanation|
|--|--|--|
|player_1 = `"rock"` <br> player_2 = `"scissors"`|`"Player 1 wins!"`|`"rock"` beats `"scissors"`|
|player_1 = `"rock"` <br> player_2 = `"rock"`|`"It's a tie!"`|`player_1` and `player_2` played the same move|
|player_1 = `"rock"` <br> player_2 = `"lizards"`|`None`|`player_2` played an invalid move, so we cannot determine a winner|

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

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 6957fd47-9dba-48b9-ac9c-38315cda0b28
* title: Gather Information
* topics: pse
##### !question

Use the box below to describe your understanding of the problem. Format the information in whatever way makes sense for you to organize your thoughts and review the contents as you continue with the upcoming prompts. Consider:
- What do we know about the problem? 
- What assumptions can we make based on the information in the problem statement? 
- What further information do the example inputs and outputs give us?

##### !end-question
##### !hint

Further questions to ask as you read through the problem statement and examples:
- What is the goal of the function?
- What are the types of the expected inputs and outputs?
- Are there any restrictions on any of the inputs?
- What do the examples show us about the values that are allowed or invalid for our inputs?
- What do the examples tell us about the return value in different scenarios?

##### !end-hint
##### !explanation 

We want to pull as much information out of the prompt and into a format that is easy for us to review and use to organize our thoughts. One of many possible examples of what this could look like:

<br>

I need to implement a function called `winner`.
- The function takes two string arguments: `player_1` and `player_2`.
- Each argument represents a move for player_1 or player_2 and will be one of the following values: 
    - "rock" 
    - "paper" 
    - "scissors"

<br>

The function should return a string indicating the result of the game:
- "Player 1 wins!" if player 1's move beats player 2's.
- "Player 2 wins!" if player 2's move beats player 1's.
- "It's a tie!" if both players make the same move.
- If either player’s move is not “rock”, “paper”, or “scissors”, return `None`

<br>

When determining who wins:
- “rock” beats "scissors"
- "scissors" beats “paper”
- “paper” beats “rock”
- If both players choose the same move, it results in a tie.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 164a62ea-f936-4c6a-8b74-6d8248ba9c9d
* title: Ask Clarifying Questions
* topics: pse
##### !question

Before you begin solving this problem, take a moment to think like a professional software engineer. What questions would you ask a teammate, product manager, or interviewer to better understand the problem before writing any code? 

<br>

List three or more questions whose answers would clarify the problem statement. For each question:
- Include information on why we are asking the question - what are we hoping to clarify by asking this?
- Provide an answer which includes the effect your decision would have on how you would approach the problem.

<br>

As you come up with questions, assume that error handling for invalid data is managed outside the function. We want to focus on questions that affect the core behavior of the function we will write. 

##### !end-question
##### !hint

- Reflect on what you stated about the problem above, what questions would give you new information?
- Assume error handling for invalid data is managed outside the function. 

##### !end-hint
##### !explanation 

The following list provides some example clarifying questions, as well as what we might decide for ourselves is the answer. Several of these questions show examples of how we might think about the same issue in different ways. For example, questions 2 and 3 are both getting at what variations in input would be considered valid or invalid. Questions 5 and 6 are about how to handle the possibility of extending the game to include more moves or more players. Notice that, even though we decide to stick with a more focused implementation for those questions, thinking through what some logical extensions might be (and in an interview context, bringing them up with the interviewer) can show that we're thinking about the problem in a broader context.

<br>

This prompt is pretty tightly specified, making it potentially more difficult to come up with clarifying questions. For future PSEs, there may be areas around edge cases, or sometimes even aspects of the core logic that may be more open to interpretation. Try to keep an eye out for areas of logic where it feels like you could make a decision about how to handle it, and then ask a question that would help you make that decision.

<br>

Try not to pose questions that are too specific to the implementation. For example, "Should I use a dictionary to store the winning combinations?" is too specific, and an interviewer is likely to leave choices about an implementation to us (and we should be prepared to justify our decisions). We should also avoid questions that change the observable behavior of a prompt. While we shouldn't ask about changing parameters or return values, or modifying behavior to something that conflicts with the prompt, we _could_ observe the requirements of the prompt, and mention how we might approach it if it were solely up to us. In an interview setting, this can give a sense of our thought process, and convey familiarity with the language over all, opening up space for a discussion. Ideally, we should think about questions that would help us understand the problem better and make decisions about how to approach it.

<br>

As stated, this list contains several questions that overlap in what they are asking as an example of different perspectives. Try not to include multiple questions about the same topic in your own questions. For example, if we ask about how to handle invalid input, we only need to ask once, not in three different ways as we have here, especially since the sample answers here are contradictory!

1. **What should happen if both users have invalid input?**
    - While both players providing invalid input could be considered a tie, I don't want the function to act as though everything was fine if an input was invalid.
    - I'll return `None` if either player has invalid input. This way, the caller can detect that something went wrong and decide how to handle it. A drawback of this approach is that the caller can't tell _which_ input was invalid, only that one of them was.
2. **Does capitalization matter?**
    - I want to know whether we need to tell the difference between “Rock” and “rock”
    - I will assume that all input will be lowercase as shown in the Rock, Paper, Scissors rules on Learn
3. **Does extra whitespace / punctuation matter?**
    - I want to know whether inputs like " rock " or "rock!" are valid or should be rejected.
    - I will assume we are getting clean input without any extra characters as shown in the Rock, Paper, Scissors rules on Learn
4. **Should anything be printed to the console?**
    - I know that we want to return the result of the match based on the problem statement, but I want to know if we should also print the result for the user to see.
    - Since the output examples do not mention anything printed out, I will assume that we are only returning the result as a string
5. **I'm familiar with a variant of rock, paper, scissors that includes additional throws (lizard and Spock). Should I keep my approach focused on the basic rules, or should I use an implementation that could be extended to game variants?**
    - I want to know if my implementation needs to be flexible enough to extend it with additional game rules.
    - While I could write a helper function that accepts a data structure that encodes the valid moves and what beats what, I'll assume that I should focus on the basic rules for now. This way, I can get a working solution faster, and if I need to extend the game later, I can refactor my code to be more flexible.
6. **When friends use rock, paper, scissors to make decisions, there are often more than two players. Should I keep my approach focused on the basic rules for 2 players?**
    - I want to know if I should I use an implementation that could be extended to support multiple players simultaneously.
    - While I could write a helper function that accepts a list of moves made by all players, the multiplayer version introduces a few complications into resolving a round that I'd like to avoid for now. I'll assume that I should focus on the basic rules for now. This way, I can get a working solution faster, and if I need to extend the game later, I can refactor my code to be more flexible.

<br>

We should keep in mind that sometimes, areas of clarification may not jump out at us when we first read the prompt. It's completely OK to think through the prompt, and even start working on it. As we start to write code, we may realize that we need to ask a clarifying question. This is a normal part of the problem-solving process. So don't feel like we need to ask all our clarifying questions before we start working on the problem.

<br>

Even if we make a decision about how to handle a particular issue here, the unit tests may lead us to reconsider that decision. For example, if we decide to return `None` for invalid input, but the unit tests expect an error to be raised, we may need to change our implementation, but there's no need to come back and update the clarifying questions. The important thing is to think through the problem and make a decision based on the information we have at the time. When the tests differ from our initial thoughts, we can think of that as a case where the interviewer has given us new information that we need to incorporate into our solution.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: d14c0645-1681-4874-ba8c-37e1bb19262d
* title: Review Clarifying Questions
* topics: pse
##### !question

While we build our skills in breaking down a problem and choosing clarifying questions, let’s use an external tool like ChatGPT to review the questions we wrote above. Our goals are to: 
- ensure we are asking questions that will tell us new information about the problem space
- check our understanding of the information we expect to get from those questions
- uncover other questions that could be useful to ask
- understand why those other questions could be helpful

<br>

For this question we will:
1. Build a prompt using [the template linked here](../shared-resources/questions-review-prompt-template.md)
2. Share the prompt with an AI tool like ChatGPT
3. Hold a discussion with the tool to ensure our understanding of what new information we would get from the initial questions submitted, and what other questions we might want to ask.
4. Reflect on the information shared by the AI tool and summarize its findings

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT 
    - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !hint

**Troubleshooting**
- If you are having issues with the tool understanding the prompt, try formatting the problem statement or examples differently.
- If you’ve reformatted the information and are still not getting useful results, reach out in #study-hall and share what you are experiencing and the link to your chat so folks can take a look and help you troubleshoot!

<br>

**Summarizing the Review**
- Did ChatGPT uncover anything about the questions you asked that you hadn’t considered?
- Did ChatGPT suggest updates to the questions you asked? 
    - If so, what updates and why?
- Did ChatGPT suggest any new questions?
    - If so, what questions and why would they be useful?

##### !end-hint
##### !explanation 

Everyone’s questions and conversation with ChatGPT will be a little different, and thus the summaries will look a little different. As an example, let’s say we used the questions and explanations below to create our prompt:

```text
1. Does capitalization matter?
    - I want to know whether we need to tell the difference between “Rock” and “rock” 
2. Does extra whitespace / punctuation matter?
    - I want to know whether inputs like " rock " or "rock!" are valid or should be rejected. 
3. Should anything be printed to the console?
    - I know that we want to return the result of the match based on the problem statement, but should we also print the result for the user? 
4. Should there be a default value for each of the arguments? 
    - I want to know whether the function is intended to be flexible and forgiving with missing inputs, or if both arguments are strictly required.
```

<br>

Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat link: https://chatgpt.com/share/682fa17f-b1a8-8005-9dec-301093934696 

<br>

I got positive feedback on the clarifying questions I asked for a coding problem. My questions about capitalization and whitespace were highlighted as especially strong, since they help define input handling. 

<br>

A couple of my other questions about printing output and default values were seen as less critical, but still thoughtful. ChatGPT suggested additional questions I could ask to better understand scope and edge cases, like whether only certain inputs are valid, if the rules could vary, or if input types are always strings. It also recommended asking about player name customization and whether the function is meant for backend use or a user interface. 

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

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

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 2bf3b413-e220-46aa-a99a-6c5f3d9715a9
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `winner` in enough detail that someone else could write the code. 

As you write your steps, keep the following guidelines in mind:
* We want to think about a general approach rather than what the code would look like line-by-line. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. 
    * For example: 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* The steps should be a description as if you were talking out the problem with another person and should be agnostic of any particular language. 
    * As such, they should not include code syntax in the description.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question
##### !placeholder

Write the logical steps here.

##### !end-placeholder
##### !explanation

It may feel cumbersome to write out the steps in detail, but it can be a helpful exercise to think through the problem before writing code. This is also a great way to practice speaking _about_ coding, which we'll need to become comfortable with for interviews and other professional settings.

<br>

In particular, talking through the steps can give an interviewer insight into whether we understand the prompt as intended, and in the event of a misunderstanding, can provide an opportunity for them to give us more information before we get too deep into an implementation. It can also help us catch potential issues early, like if we realize that we're not sure how to handle a certain edge case, or that we're not sure how to implement a certain part of the logic.

<br>

During an interview, we'd still want to be careful not to spend _too_ much time on this step. Mostly we'd like to get an overall sense of the problem and an outline of how we might approach it, then move on to writing code. But during PSEs, we'd like a bit more detail for the practice.

<br>

Example steps:

1. Check whether both player_1 and player_2 are one of "rock", "paper", or "scissors"
    - if not, return None
2. Check for a tie: 
    - if player_1 is the same as player_2, return "It's a tie!"
3. First deal with the case that player_1 is "rock"
    - if player_2 is "scissors", return "Player 1 wins!"
    - otherwise (player_2 must be "paper"), return "Player 2 wins!"
4. Next deal with the case that player_1 is "paper"
    - if player_2 is "rock", return "Player 1 wins!"
    - otherwise (player_2 must be "scissors"), return "Player 2 wins!"
5. Otherwise player_1 must be "scissors"
    - if player_2 is "rock", return "Player 2 wins!"
    - otherwise (player_2 must be "paper"), return "Player 1 wins!"

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: eb41ea7a-cbdf-46d7-b48d-a03bebe872f7
* title: Review Logical Steps
* topics: pse
##### !question

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. Let’s once more use ChatGPT, this time to review the Logical Steps we wrote above. Our goals are to check if:
- the steps make sense for the problem being solved
- the steps are not missing important steps or scenarios
- the steps are agnostic of any particular language – steps should not include code syntax.
- the steps are written with enough detail for another person to understand how to create a solution to the problem description

<br>

For this question we will:
1. Build a prompt using [the template linked here](../shared-resources/steps-review-prompt-template.md)
2. Share the prompt with an AI tool like ChatGPT
3. Hold a discussion with the tool to ensure our Logical Steps meet the goals listed above and understand areas where we could add clarity or better meet our goals
4. Reflect on the information shared by the AI tool and summarize its findings

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
   - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !explanation

As an example, let’s say we used the logical steps in the explanation for the question above in our prompt. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: 
https://chatgpt.com/share/682fa106-d1f8-8005-9313-6471c059de62

<br>

ChatGPT said my approach to solving the Rock, Paper, Scissors problem was clear, mostly well-structured, and logically sound. It gave positive feedback around how I handled input validation, ties, and all win/loss scenarios, which showed I understood the rules. Overall, my steps were detailed enough for someone else to implement a solution.

<br>

I was reminded to make my explanation more language-agnostic since terms like “if” and “return” felt a bit too close to code. ChatGPT suggested softening that language and focusing more on logic than syntax. ChatGPT also shared I could improve my steps by:
- clearly labeling each step by purpose (e.g., validation, tie check, winner logic) 
- clarifying that input validation is only needed when bad inputs are possible

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

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
    elif player_1 == "paper":
        if player_2 == "rock":
            return "Player 1 wins!"
        else:
            return "Player 2 wins!"
            
    # player 1 = scissors
    else:
        if player_2 == "rock":
            return "Player 2 wins!"
        else:
            return "Player 1 wins!"
```

### !end-explanation
<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, hidden, students click to view) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
<!-- !explanation - !end-explanation (markdown, students can see after answering correctly) -->
### !end-challenge
<!-- prettier-ignore-end -->

