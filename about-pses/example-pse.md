# Activity: Example PSE

## Problem Statement

Imagine working on software for a game of [Rock, Paper, Scissors](https://en.wikipedia.org/wiki/Rock_paper_scissors).

Create a function named `winner` that takes two arguments, the move for `player_1` and `player_2` (`"rock"`, `"paper"`, or `"scissors"`), and returns the winner (`"Player 1 wins!"`, `"Player 2 wins!"`, or `"It's a tie"`).

## Example Input/Output

| Input (Argument of the function) | Expected Output (Return value of the function) | Explanation|
|--|--|--|
|player_1 = `"rock"` <br> player_2 = `"scissors"`|`"Player 1 wins!"`|`"rock"` beats `"scissors"`|
|player_1 = `"rock"` <br> player_2 = `"rock"`|`"It's a tie!"`|`player_1` and `player_2` played the same move|

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
* title: Describe Your Understanding
* topics: pse
##### !question

Before you begin solving this problem, take a moment to think like a professional software engineer. 
- What do we know about the problem? 
- What assumptions can we make based on the information in the problem statement? 
- What further information do the example inputs and outputs give us?
- What questions would you ask a teammate, product manager, or interviewer to better understand the problem before writing any code?

<br>

In the box below, list 5 or more observations about the problem or questions whose answers would clarify the problem statement. For each observation or question, include information on why that observation is important or why you are asking the question
- For each observation, answer how that observation will affect your approach to the problem
- For each question, describe what you are hoping to clarify about the problem and provide an answer which includes the effect your decision would have on how you might approach the problem.

<br>

As you come up with observations and questions, assume that error handling for invalid data is managed outside the function. We want to focus on the core behavior of the function we will write. Examples of invalid data we don't need to manage may include:
- Mismatched data types: If a function expects a string, you may assume it will receive a string. This follows for nested data as well.
- String Sanitization: You may assume strings will not include invalid characters.

##### !end-question
##### !placeholder

Add observations, assumptions, and questions here:

1. From the problem description, I observe that...
2. In the example inputs I can see...
3. A question I have around inputs is...
4. Based on the requirements, I am making the assumption...
5. What behavior is expected when...

##### !end-placeholder
##### !hint

Further questions to ask as you read through the problem statement and examples:
- What is the goal of the function?
- What are the types of the expected inputs and outputs?
- Are there any restrictions on any of the inputs?
  - For example: if any of the inputs are a list, do we know anything about how the list is ordered?
- What do the examples show us about the data types and values that are allowed for our inputs?
- What do the examples tell us about the return value in different scenarios?
- Reflecting on the observations you have made so far, what questions would give you new information?

##### !end-hint
##### !explanation 

We want to pull as much information out of the prompt as we can and format that info in a way that is easy for us to review and use to organize our thoughts. 

<br>

This prompt is pretty tightly specified, making it potentially more difficult to come up with clarifying questions in addition to observations. For future PSEs, there may be areas around edge cases, or sometimes even aspects of the core logic that may be more open to interpretation. Try to keep an eye out for areas of logic where it feels like you could make a decision about how to handle it, and then ask a question that would help you make that decision!

<br>

When coming up with questions, try not to pose questions that are too specific to the implementation. For example, "Should I use a dictionary to store the winning combinations?" is too specific. An interviewer is likely to leave choices about an implementation to us (and we should be prepared to justify our decisions). 

<br>

We should also avoid questions that change the observable behavior of a prompt. While we shouldn't ask about changing parameters or return values, or modifying behavior to something that conflicts with the prompt, we could observe the requirements of the prompt, and mention how we might approach it if it were solely up to us. 

<br>

In an interview setting, this can give a sense of our thought process, and convey familiarity with the language over all, opening up space for a discussion. Ideally, we should think about observations and questions that would help us understand the problem better and make decisions about how to approach it.

<br>

One of many possible sample responses could look like:

<br>

1. I need to implement a function called `winner` that takes two arguments: `player_1` and `player_2`.
    - This means I need to create a function definition with two parameters named exactly `player_1` and `player_2`.

2. Each argument represents a move for `player_1` or `player_2` and will be one of "rock", "paper", or "scissors".
    - The values shown are strings, so I can assume the inputs will be strings holding one of these 3 values and that I will need to compare the strings in some way to find a winner.

3. The function should return a string indicating the result of the game: "Player 1 wins!", "Player 2 wins!", or "It's a tie!"
    - Aside from checking if someone wins, I need to consider the edge case where the players could tie.

4. The second input/output example shows both players choosing "rock" and the result is a tie
    - I am hypothesizing that two players choosing the same move results in a tie. 
    - This is supported by the table of rules further below that shows the result as "It's a tie!" any time both players choose the same move.

5. The table of rules contains text "input (first argument)" and "input (second argument)"
    - This tells me when deciding who is the winner, I need to be mindful that the first argument's value always represents player_1 and the second argument represents player_2.
    - This is supported by the first example where `player_1 = "rock"` and `player_2 = "scissors"`, and the result was `"Player 1 wins!"`.

6. Based on the table of rules: "rock" beats "scissors", "scissors" beats "paper", "paper" beats "rock".
    - When developing my solution, I will use these rules to guide the conditional statements I need to write to determine the winner.

<br>

We should keep in mind that sometimes, areas of clarification may not jump out at us when we first read the prompt. It's completely OK to think through the prompt, and even start working on it. As we start to write code, we may note something we missed before or realize that we need to ask a clarifying question. 
- This is a normal part of the problem-solving process! We don't need to note everything or ask all our clarifying questions before we start working on the problem.

<br>

Even if we make a decision about how to handle a particular issue here, the unit tests may lead us to reconsider that decision. If that happens, it's okay and is a part of the development process! There's no need to come back and update the "Describe Your Understanding" section. 
- The important thing is to think through the problem and make a decision based on the information we have at the time. 
- When the tests differ from our initial thoughts, we can think of that as a case where the interviewer has given us new information that we need to incorporate into our solution.

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
    
When naming a test, we want to ensure the name describes the scenario we are testing by including information like the function being tested, inputs, and expected outputs. 

For example, if we wanted to test that the function `winner` returns a tie when `player_1` and `player_2` have the same value, then we might name the test something like `test_winner_returns_tie_for_players_with_same_value`.
* This may not seem useful here where we are only writing two tests, but building strong naming habits now will benefit us once we're in production environments where a single function or component may have dozens of tests that we need to be able to quickly distinguish from each other.

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

Consider writing tests that capture decisions you made when reviewing your observations and clarifying questions. For example, in the sample observations, we noted that from the rules and examples we know that either player could win, or there could be a tie – which could be a positive edge case. For code in a production environment, we would want to check all of the possible scenarios, but for a PSE, we can pick either player winning with "rock", "paper", or "scissors" as our nominal test case and use one of the tie scenarios as a positive edge case.

<br>

Example input/output and tests:

```python
# example input 1: player_1 = "rock", player_2 = "scissors"
# expected output 1: "Player 1 wins!"

# example input 2: player_1 = "rock", player_2 = "rock"
# expected output 2: "It's a tie!"

def test_winner_player_1_rock_beats_scissors():
    # arrange
    player_1 = "rock"
    player_2 = "scissors"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == "Player 1 wins!"

def test_winner_both_rock_results_in_tie():
    # arrange
    player_1 = "rock"
    player_2 = "rock"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == "It's a tie!"  
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

Without writing code, describe how you would implement `winner` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
* The objective is to practice describing algorithms and technical concepts while creating a roadmap that we can use to keep ourselves oriented towards our goal during the implementation step.
* It is okay to leave some of the finer details to be worked out in the implementation itself!

As you write your steps, keep the following guidelines in mind:
* We want to think about a general approach rather than what the code would look like line-by-line. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. 
    * For example: 1. Handle edge cases, 2. Perform the computation/solve the problem/etc.
* The steps should be a description as if you were talking out the problem with another person and should be agnostic of any particular language. 
    * As such, they should not include code syntax in the description.

What's important at this stage is to think through how you would put an approach into words, and outline the implementation before writing code.

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
1. First, we'll handle our simplest case which is checking for a tie: 
    - if `player_1` is the same as `player_2`, return "It's a tie!"
2. If it is not a tie, we'll move through the cases where `player_1` is "rock", "paper", or "scissors" to determine a winner, starting with the case that player_1 is "rock":
    - if player_2 is "scissors", return "Player 1 wins!"
    - otherwise player_2 must be "paper", return "Player 2 wins!"
3. Next we'll deal with the case that player_1 is "paper":
    - if player_2 is "rock", return "Player 1 wins!"
    - otherwise player_2 must be "scissors", return "Player 2 wins!"
4. Otherwise player_1 must be "scissors":
    - if player_2 is "rock", return "Player 2 wins!"
    - otherwise player_2 must be "paper", return "Player 1 wins!" 

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

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. While we build our skills in breaking down and describing algorithms, let’s use an AI tool like ChatGPT to review the Logical Steps we wrote above. Our goals are to check if the steps:
- convey the technical concepts and requirements of the problem in a way that another person can understand
- make sense for the problem being solved
- are not missing important steps or scenarios
- are agnostic of any particular language – the steps should not include code syntax.

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/670252696f1625cf0ed77c0997cd165d/raw/pse_logical_steps_review_template.md)
2. Share the completed prompt with an AI tool like ChatGPT
3. Reflect on the information shared by the AI tool, then use the prompts below to summarize its findings and your learnings.

<br>

Reflection Prompts

1. Identify one specific strength the AI highlighted in your explanation. 
    * Quote or paraphrase the part of the feedback that mentions this strength, and explain why you think that aspect of your explanation was effective.
2. Point out at least one specific improvement the AI recommended.
    * Describe exactly which part of your explanation would benefit from strengthening then outline how you would revise that part if you were rewriting it now.
3. Identify one piece of AI feedback you believe was inaccurate, irrelevant, or unnecessary. 
    * Explain why it doesn’t apply to this problem, and cite a source (docs, class notes, instructor explanation, or trusted online reference) that supports your reasoning.
4. Describe one change the AI suggested that was new or surprised you. 
    * Share how this suggestion shifted your understanding of the problem or your explanation.

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
    - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !explanation

As an example, let’s say we used a slightly modified version of the sample response from the "Logical Steps" question above to fill in the prompt template. In this example, the only change is that we refer to checking for a tie as an "edge case" in the first step.

<br>

Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

*Note:*
Depending on exactly what the AI shares, a reflection and summary might look like:

<br>

Chat Link: [https://gist.github.com/ada-instructors/56c872acec770c68a9ae8b81b58a80a1](https://gist.github.com/ada-instructors/56c872acec770c68a9ae8b81b58a80a1)

<br>

*Note:*

*We are using a gist link in this example to ensure that the link exists from cohort to cohort. When submitting your response, the link should be a shareable link to your chat in the AI tool where you held the conversation.*

<br>

One strength the AI highlighted was my use of "otherwise... must be" phrasing throughout my steps. The feedback noted that this showed I understood "that earlier conditions have already eliminated other possibilities," which is the kind of reasoning interviewers want to see. I think this worked well because it demonstrates I wasn't just listing cases mechanically, I was actively narrowing down what remained, which makes the logic easier to follow and verify.

<br>

The main improvement the AI recommended was dropping the term "edge case" when describing the tie condition. My explanation currently calls it an edge case to justify handling it first, but the feedback pointed out that a tie isn't unusual, it occurs roughly a third of the time. If I were rewriting that step, I'd say something like "we check for a tie first because it's the simplest condition to eliminate, and removing it upfront reduces the branching we need below." 

<br>

Around irrelevant feedback, the AI flagged that I was implicitly assuming valid input and suggested I acknowledge that assumption explicitly. I'd push back on this suggestion for this problem since the problem statement itself defines the inputs as exactly "rock", "paper", or "scissors", so there's no ambiguity to address. According to how my instructors have framed problem-solving exercises, we're expected to work within the constraints given, not expand scope by handling cases the problem rules out. Calling that a gap feels like feedback written for a different, more open-ended problem. 

<br>

Finally, I was genuinely surprised by the reframe around why to handle the tie first. I thought I was identifying it as a special case, but the feedback reframed it as a deliberate structural choice that simplifies the logic below it. That shift from "this is different" to "this makes everything else cleaner" changes how I'll think about ordering conditions in future problems.

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
def test_winner_player_1_rock_beats_scissors():
    # arrange
    player_1 = "rock"
    player_2 = "scissors"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == "Player 1 wins!"

def test_winner_both_rock_returns_tie():
    # arrange
    player_1 = "rock"
    player_2 = "rock"

    # act
    result = winner(player_1, player_2)

    # assert
    assert result == "It's a tie!"  
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
    def test_winner_both_rock_returns_tie(self):
        # Arrange / Act
        result = winner("rock", "rock")

        # Assert
        self.assertEqual(result,"It's a tie!")

    def test_winner_both_scissors_returns_tie(self):
        # Arrange / Act
        result = winner("scissors", "scissors")

        # Assert
        self.assertEqual(result,"It's a tie!")

    def test_winner_both_paper_returns_tie(self):
        # Arrange / Act
        result = winner("paper", "paper")

        # Assert
        self.assertEqual(result,"It's a tie!")

    def test_winner_player_1_rock_beats_scissors(self):
        # Arrange / Act
        result = winner("rock", "scissors")

        # Assert
        self.assertEqual(result, "Player 1 wins!")

    def test_winner_player_2_rock_beats_scissors(self):
        # Arrange / Act
        result = winner("scissors","rock")

        # Assert
        self.assertEqual(result,"Player 2 wins!")

    def test_winner_player_1_scissor_beats_paper(self):
        # Arrange / Act
        result = winner("scissors","paper")

        # Assert
        self.assertEqual(result, "Player 1 wins!")

    def test_winner_player_2_scissors_beats_paper(self):
        # Arrange / Act
        result = winner("paper","scissors")

        # Assert
        self.assertEqual(result,"Player 2 wins!")

    def test_winner_player_1_paper_beats_rock(self):
        # Arrange / Act
        result = winner("paper", "rock")

        # Assert
        self.assertEqual(result, "Player 1 wins!")

    def test_winner_player_2_paper_beats_rock(self):
        # Arrange / Act
        result = winner("rock","paper")

        # Assert
        self.assertEqual(result,"Player 2 wins!")
```
### !end-tests
### !explanation

An example of a working implementation:

```python
def winner(player_1, player_2):
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

