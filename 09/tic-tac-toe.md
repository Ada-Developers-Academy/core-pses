# Tic Tac Toe

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
##### !placeholder

Add observations, assumptions, and questions here:

Eg. from the sample PSE: 
I observe that the function should return a string indicating the result of the game: "Player 1 wins!", "Player 2 wins!", or "It's a tie!"
    - Aside from checking if someone wins, I need to consider the edge case where the players could tie.

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

2. Based on the examples, whether they are `'X'` or `'O'`, a winner needs to get 3 in a row, and this could be done vertically, horizontally, or diagonally. 
    - I can do something like hard code the indices of the matrix cells I need to check for each win location, or I can loop over the board in a few different ways to be able to check for a win condition.

3. Does the board need to be full for someone to win?
    - This would affect how we need to check the board for a win since we would need to check all cells, not just for 3 matching `'X'`s or `'O'`s in a row. 
    - This isn't explicitly described in the problem statement, but digging into the rules of tic tac toe, the game ends when the first person reaches 3 in a row, so there could be spots on the board that were not used.
    - This is supported by example 3 where there is a diagonal `'X'` win with empty spots left on the board, so I will assume that boards do not need to be full for there to be a winner.

4. What should the function return if two players have both won? For example: 3 `'O'`s across the top and 3 `'X'`s across the bottom row?
    - This scenario isn't captured in the problem statement or examples. In a standard game of tic tac toe, there can only be one winner and the game ends when the first person reaches 3 in a row, so I will assume boards can only have one winner and I will return the first winner found on the board. 

5. Thinking about when we should return `None` or 'Tie' for a game still in progress, I only need to consider these states if a winner cannot be found. 
    - The problem statement says to return `None` "for a game that is still in progress and has no winner", and to return 'Tie' for a board with no winner and no places left to make moves. Both of these scenarios depend on there being no winner on the board, which I will only know if I check for winners first. 

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

When naming a test, we want to ensure the name describes the scenario we are testing by including information like the function being tested, inputs, and expected outputs. 
* e.g. from the example PSE: if we wanted to test that the function winner returns a tie when `player_1` and `player_2` have the same value, then we might name the test something like `test_winner_both_inputs_paper_returns_tie`.

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
# nominal test case
def test_tic_tac_toe_winner_row_win_x():
    # Arrange
    board = [['X', 'X', 'X'],
             ['O', 'O', ''],
             ['', '', 'O']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result == 'X'

# edge test case
def test_tic_tac_toe_winner_empty_board_returns_none():
    # Arrange
    board = [['', '', ''],
             ['', '', ''],
             ['', '', '']]

    # Act
    result = tic_tac_toe_winner(board)

    # Assert
    assert result is None

# alternative nominal test case
def test_tic_tac_toe_no_winner_returns_tie():
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

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: dfe2e816-9e1d-411d-84db-fd086fe82027
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `tic_tac_toe_winner` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency.
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
### !explanation

Example Steps:

1. Check for a winner `X` or `O`:
   1. Loop over the input matrix by row, checking if each element of the row is the same and is not an empty string. If so, return the first element of the row.
   2. Loop over the input matrix by column, checking if each element of the column is the same and is not an empty string. If so, return the first element of the column.
   3. Check the indices for the left to right diagonal and right to left diagonal. If the strings are all the same and are not empty for either of the diagonals, return the first element of that diagonal.
2. If we have not returned by this point, check for "Tie" or ongoing game:
    1. Loop over the input row by row and check for any empty strings. If there are empty strings, moves can still be made so we will return `None` for a game still in progress.
    2. If the loop ends and we have not returned, then return `Tie` since the board must be full and there is no winner.

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 4dddccc4-3815-4e20-b39b-b7ef8fa5bae0
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

As an example, let’s say we used the logical steps in the explanation for the question above in our prompt. Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: `<url to your conversation>`

<br>

One strength the AI tool highlighted was that my approach correctly covered all required game states and separated winner detection from board-state (tie or in progress) detection in a clear, logical order. The steps will map well to the code I will write and will be easy for another person to understand.

<br>

One improvement the AI recommended was to spend more time explaining why the approach works, such as why checking rows, columns, and diagonals covers all possible winning conditions and why winner detection should occur before tie detection. I also could include explicit statements as to which kind of win each step is checking for rather than implying that within the details of the step.

<br>

I didn't really find any of the feedback to be unnecessary. Most of the feedback focused on how to strengthen the explanation by adding more details and clarifying the reasoning behind the approach. There were some suggestions that I felt were minor quibbles, but it's still useful to have examples of how an interviewer might prefer me to explain things. Since Tic Tac Toe is generally considered to be a children's game, I think I took a lot of things for granted in my own thinking. But there's actually quite a bit to think through in terms of how to explain the approach clearly and thoroughly, and I can see how the feedback is helpful for improving my communication of technical concepts.

<br>

One suggestion that surprised me was the recommendation to explicitly explain why a full board should not be checked before checking for a winner. Although that ordering felt obvious to me, I can see how calling it out demonstrates a deeper understanding of the problem. Since the board is relatively small, and the problem is related to a children's game, it's easy to overlook the implied ordering of the steps since our brains just do it in a way that feels "all at once". This could be an opportunity to also describe why the ordering of the individual win checks (row, column, diagonal) does not matter as long as they are all checked before checking for tie or ongoing game. This would be interesting because this is related to how this logic would get used (e.g. in a real game of tic tac toe, this logic would be run after each move, meaning there would only be one new potential win condition to check after each move).

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
