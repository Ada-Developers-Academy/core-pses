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
- Reflect on the observations you have made so far, what questions would give you new information?
- Assume error handling for invalid data is managed outside the function. 

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

2. Each argument represents a move for player_1 or player_2 and will be one of "rock", "paper", or "scissors".
    - The values shown are strings, so I can assume the inputs will be strings holding one of these 3 values and that I will need to compare the strings in some way to find a winner.

3. The function should return a string indicating the result of the game: "Player 1 wins!", "Player 2 wins!", or "It's a tie!"
    - Aside from checking if someone wins, I need to consider the edge case where the players could tie

4. The second input/output example shows both players choosing "rock" and the result is a tie
    - I am hypothesizing that two players choosing the same move results in a tie. 
    - This is supported by the table of rules further below that shows the result as "It's a tie!" any time both players choose the same move.

5. The table of rules contains text "input (first argument)" and "input (second argument)"
    - This tells me when deciding who is the winner, I need to be mindful that the first argument's value always represents player_1 and the second argument represents player_2
    - This is supported by the first example where `player_1 = "rock"` and `player_2 = "scissors"`, and the result was `"Player 1 wins!"`

6. Based on the table of rules: "rock" beats "scissors", "scissors" beats "paper", "paper" beats "rock"
    - When developing my solution, I will use these rules to guide the conditional statements I need to write to determine the winner

<br>

We should keep in mind that sometimes, areas of clarification may not jump out at us when we first read the prompt. It's completely OK to think through the prompt, and even start working on it. As we start to write code, we may note something we missed before or realize that we need to ask a clarifying question. This is a normal part of the problem-solving process. So don't feel like we need to note everything or ask all our clarifying questions before we start working on the problem.

<br>

Even if we make a decision about how to handle a particular issue here, the unit tests may lead us to reconsider that decision. If that happens, it's okay and is a part of the development process! There's no need to come back and update the "Describe Your Understanding" section. 
- The important thing is to think through the problem and make a decision based on the information we have at the time. 
- When the tests differ from our initial thoughts, we can think of that as a case where the interviewer has given us new information that we need to incorporate into our solution.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: d14c0645-1681-4874-ba8c-37e1bb19262d
* title: Review Observations & Questions
* topics: pse
##### !question

While we build our skills in breaking down a problem and choosing clarifying questions, let’s use an external tool like ChatGPT to review the observations and questions we wrote while describing our understanding. 

<br>

Our goals are to: 
- confirm if our observations and assumptions make sense in the context of the code problem
- ensure we are asking questions that will tell us new information about the problem space
- check our understanding of the information we expect to get from those questions
- uncover other observations that would help shape our approach and understand how they would affect our approach
- uncover further questions that could be useful to ask and understand why those other questions could be helpful

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/16c97dc4b16ab2bf449d9d7a81caeb16/raw/pse_observations_questions_review_template.md )
2. Share the filled in prompt with an AI tool like ChatGPT
3. After the initial review, ask *at least one* follow up question using the AI tool that furthers your understanding of the problem and why certain observations or questions are useful. Some examples could be asking questions to: 
    - ensure your understanding of the analysis of the observations
    - get more details on the information we could get from asking particular questions
    - learn more about new information shared by the tool
4. Reflect on the information shared by the AI tool and summarize its findings and your learnings

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
- Did the AI tool uncover anything about the observations you made that you hadn’t considered?
- Did the AI tool uncover anything about the questions you asked that you hadn’t considered?
- Did the AI tool suggest updates to the observations you made or questions you asked? 
    - If so, what updates and why?
- Did the AI tool suggest any new observations or questions?
    - If so, what? Why would they be useful?

##### !end-hint
##### !explanation 

Everyone’s observations & questions, and conversation with ChatGPT will be a little different, thus, the summaries will look a little different. As an example, let’s say we used the sample response from "Describe Your Understanding" above to fill in the prompt template.

<br>

Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

** Note ** 
We are using a gist link in this example to ensure that the link exists from cohort to cohort. When submitting your response, the link should be a shareable link to your chat in the AI tool where you held the conversation.

<br>

Chat link: [https://gist.github.com/ada-instructors/8d1dd2bcb00e3ce86ca061c5f2509c14](https://gist.github.com/ada-instructors/8d1dd2bcb00e3ce86ca061c5f2509c14) 

<br>

I received positive feedback that my observations about the coding problem were clear, accurate, and well-supported by the examples and rules provided, such as my reasoning about how the rules work (like same move = tie and player position matters). I didn't list any clarifying questions, so I got suggestions for some around whether the inputs are guaranteed to be lowercase or always valid. These questions help reveal if I need to handle errors or normalize data, even though those aspects are outside the scope of the PSE. 

<br>

One helpful insight was that there are only nine possible input combinations, making it easy to fully test the function. This makes testing straightforward because the entire input space is small, finite, and fully specified. The feedback encouraged me to keep cross-checking examples with logic and to ask clarifying questions early.

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

Without writing code, describe how you would implement `winner` in enough detail that another Python developer could reasonably implement a solution. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
- The objective is to create a roadmap that we can use to keep ourselves oriented towards our goal
- It is okay to leave some of the finer details to be worked out in the implementation itself!

As you write your steps, keep the following guidelines in mind:
* We want to think about a general approach rather than what the code would look like line-by-line. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. 
    * For example: 1. Handle edge cases, 2. Perform the computation/solve the problem/etc.
* The steps should be a description as if you were talking out the problem with another person and should be agnostic of any particular language. 
    * As such, they should not include code syntax in the description.

What's important at this stage is to think through and outline the implementation before writing code.

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
1. Check for a tie: 
    - if player_1 is the same as player_2, return "It's a tie!"
2. First deal with the case that player_1 is "rock"
    - if player_2 is "scissors", return "Player 1 wins!"
    - otherwise player_2 must be "paper", return "Player 2 wins!"
3. Next deal with the case that player_1 is "paper"
    - if player_2 is "rock", return "Player 1 wins!"
    - otherwise player_2 must be "scissors", return "Player 2 wins!"
4. Otherwise player_1 must be "scissors"
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

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. Let’s once more use an AI tool like ChatGPT, this time to review the Logical Steps we wrote above. Our goals are to check if:
- the steps make sense for the problem being solved
- the steps are not missing important steps or scenarios
- the steps are agnostic of any particular language – steps should not include code syntax.
- the steps are written with enough detail for another Python developer to understand how to create a solution

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/670252696f1625cf0ed77c0997cd165d/raw/pse_logical_steps_review_template.md)
2. Share the filled in prompt with an AI tool like ChatGPT
3. After the initial review, ask *at least one* follow up question using the AI tool. We want to ask questions that help us understand: 
    - areas where we could add clarity
    - edge cases we might have missed
    - places where our steps do not meet the expectations of the problem statement
4. Reflect on the information shared by the AI tool and summarize its findings and your learnings

<br>

In the box below, please submit:
1. A shareable link to your conversation in ChatGPT
    - [Documentation for creating a shareable link in ChatGPT](https://help.openai.com/en/articles/7925741-chatgpt-shared-links-faq)
2. Your reflections and summary of the discussion with ChatGPT

##### !end-question
##### !explanation

As an example, let’s say we used the sample response from the "Logical Steps" question above to fill in the prompt template. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

** Note ** 
We are using a gist link in this example to ensure the link exists from cohort to cohort. When submitting your response, the link should be a shareable link to your chat in the AI tool where you held the conversation.

<br>

Chat Link: [https://gist.github.com/ada-instructors/56c872acec770c68a9ae8b81b58a80a1](https://gist.github.com/ada-instructors/56c872acec770c68a9ae8b81b58a80a1)

<br>

I received feedback that my approach was clear, and my logical steps that didn’t rely on Python specific syntax, which made it easy to understand. I made good use of logic by handling ties first and explaining each outcome clearly, showing I understood the reasoning behind the rules. 

<br>

An area mentioned for improvement is to keep my language more consistent in how I describe outcomes and reasoning. For example, I could phrase outcomes in a way that explains why a player wins, not just that they win. Another suggestion was to consider alternative ways of structuring the logic, like grouping by winning relationships (e.g., “rock beats scissors”). This structure shows I grasp the underlying game logic, not just how to implement it procedurally. 

<br>

Overall, I’m on the right track, and with small tweaks to my phrasing and logic organization, I can make my solutions even stronger and more flexible.

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

