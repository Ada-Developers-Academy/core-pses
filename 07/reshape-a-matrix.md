# Reshape the Matrix

## Problem

In MATLAB, a programming platform for numeric computing, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different dimensions while keeping its original data.

You're given a matrix represented by a two-dimensional array, and two positive integers **rows** and **columns** representing the number of rows and number of columns respectively of the intended reshaped matrix.

The reshaped matrix needs to be filled with all the elements of the original matrix in the same row-traversing order as they originally appeared.
- If the 'reshape' operation with given parameters is possible, output the new reshaped matrix.
- Otherwise, raise a `ValueError` (You may choose the specific error message)

**Example 1:**

```
Input: 
nums = 
[[1, 2],
 [3, 4]]
rows = 1, columns = 4

Result: 
[[1, 2, 3, 4]]
```

**Explanation:** The row-traversing of nums is [1,2,3,4]. The new reshaped matrix is a 1 * 4 matrix, fill it row by row by using the values in the order they appear in the original matrix.


**Example 2:**

```
Input: 
nums = 
[[1, 2],
 [3, 4]]
rows = 2, columns = 4

Result: 
ValueError
```

**Explanation:** There is no way to reshape a 2 * 2 matrix to a 2 * 4 matrix, so we raise a ValueError.

**Example 3:**

```
Input: 
nums = 
[[1, 2],
 [3, 4],
 [5, 6],
 [7, 8]]
rows = 2, columns = 4

Result: 
[[1, 2, 3, 4],
 [5, 6, 7, 8]]
```

**Explanation:** The original matrix was 4 * 2. The new reshaped matrix is a 2 * 4 matrix, fill it row by row by using the values in the order they appear in the original matrix.

**Note:**

It can be assumed that all given `rows` and `columns` are positive numbers.

Sourced from:  [Leetcode](https://leetcode.com/problems/reshape-the-matrix/)

## Prompts:

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 931b7218-6fc5-4fd5-9b6c-7945856a6041
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

1. The last two bullet points of the description say that we should output a new matrix or raise a ValueError.
    - This tells me that the only expected return value of the function should be a new matrix if reshaping is possible.

2. The problem statement says the matrix we receive as an argument will be represented as a 2 dimensional array. In the examples, the outputs are also displayed as 2 dimensional arrays.
    - This means that the new matrix we create should also be a 2 dimensional array.

3. When discussing the output, it says we should raise a ValueError if the original matrix cannot be reshaped as requested.
    - I will need to do some check in my function to see if the number of items in the original matrix is equal to the number of items in the requested matrix before trying the reshape operation.

4. The problem statement says the new matrix needs to be filled with the elements of the old matrix in the same row-traversing order.
    - This means that the order of the elements in the new matrix matters. I will need to go row by row starting at the front of each list in the original matrix as I fill up the new matrix.

5. We can assume that the arguments to the function will be valid, so the input matrix will be a nested list with a consistent number of `rows` and `columns`, and the `rows` and `columns` will not be negative. We have also been given the note "It can be assumed that all given `rows` and `columns` are positive numbers." 
    - This means that the implementation does not need to worry about a case where the input matrix is empty or how an empty matrix might be represented in this scenario, as it is unclear what the definition of an empty matrix could be for this problem. (For example `[]` reports 0 rows, but would error if we try to read the columns and `[[]]` reports 0 columns, but 1 row).

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: code-snippet
* language: python3.6
* id: fad6f341-46a3-493f-81ea-6d9325a77180
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `reshape_matrix` for the nominal and edge cases you identified in the first step.

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
def test_reshape_matrix_1_by_4_can_reshape_into_4_by_1():
    # Arrange
    matrix = [[1], [2], [3], [4]]
    rows = 1
    columns = 4

    # Act
    result = reshape_matrix(matrix, rows, columns)

    # Assert
    assert result == [[1, 2, 3, 4]]

# edge test case
def test_reshape_matrix_2_by_2_raises_error_reshaping_to_4_by_2():
    # Arrange
    matrix = [[1, 2], [3, 4]]
    rows = 4
    columns = 2

    # Act & Assert
    with pytest.raises(ValueError):
        reshape_matrix(matrix, rows, columns)
```
##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 1ece1eb2-0d72-4068-9ca6-f77ca49d73c5
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `reshape_matrix` as if you were talking through the details with another developer who will have to implement the function. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency.
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

1. Check if the reshape can be done:
    - See if the number of elements in the original matrix (number of rows multiplied by the number of columns) matches the number of elements in the desired output (the argument `rows` multiplied by the argument `columns`).
    - If the reshape cannot be done, raise a `ValueError`
2. Create an empty list where we'll store the rows of the new matrix for our return value
3. Iterate through the input matrix in order. 
4. For each element in the original matrix: 
    - Check if we should start a new row in the output matrix. We should start a new row once the current row reaches the input `column` total elements. This new row should be appended to the list holding the rows of our output matrix.
    - Append the value from the input matrix to the row we are building in the output matrix
5. Once we have iterated through all of the values in the input matrix, return the output matrix

### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 2ad12c37-4a7c-41fa-9bf9-8fa91f68bda1
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

As an example, let’s say we used logical steps similar to the explanation for the question above in our prompt. Depending on how the supplied steps differ and exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: `<url to your conversation>`

<br>

One strength the AI tool pointed out was that I correctly identified the feasibility check for the reshape operation. The feedback stated that I "immediately identified that original rows × original columns must equal target rows × target columns" and described this as the most important observation in the problem. I think this aspect of my explanation was effective because it demonstrates an understanding of the fundamental constraint of matrix reshaping. Before attempting to build the new matrix, it is necessary to verify that the total number of elements remains the same. 

<br>

One improvement the AI recommended was making my explanation of the row-building process more precise. In my original explanation, I stated that a new row should be started "once the current row reaches the input `column` total elements". Although I intended "column" to refer to the function argument named `columns`, the wording could be interpreted as referring to the number of columns in the original matrix. If I were rewriting my explanation, I would state that a new row should be started once the current output row contains `columns` elements. This revision would make the explanation clearer and reduce the chance of misunderstanding during an interview.

<br>

One piece of feedback that I believe was inaccurate was the claim that my algorithm would not correctly reshape the matrix because I was using the original matrix's column count when deciding when to start a new row. After clarifying my explanation, it became clear that I was actually referring to the function argument `columns`, which represents the target number of columns in the reshaped matrix. Because of this misunderstanding, the feedback addressed a problem that did not exist in the intended algorithm. The issue was not the logic itself but the ambiguity of my wording.

<br>

One suggestion that stood out to me was the recommendation to explain not only what the algorithm does but also why it works. The AI pointed out that I described the steps of my solution but could strengthen my explanation by connecting those steps to the problem requirements. This shifted my understanding of interview communication because I realized that interviewers are often looking for evidence of reasoning, not just a list of actions. If I were explaining the solution again, I would mention that iterating through the matrix in row-traversal order preserves the original ordering of the elements, which is exactly what the problem requires.

<br>

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->