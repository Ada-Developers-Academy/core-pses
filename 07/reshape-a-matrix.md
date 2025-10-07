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
* type: paragraph
* id: b031f26b-0f64-4f58-99e8-f6fc4ea3ee63
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
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/16c97dc4b16ab2bf449d9d7a81caeb16/raw/pse_observations_questions_review_template.md)
2. Share the completed prompt with an AI tool like ChatGPT
3. After the initial review, ask the AI tool *at least one* follow up question that furthers your understanding of the problem and why certain observations or questions are useful. Some examples could be asking questions to: 
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

For an example of what a review response might look like, let’s say that we provided observations similar to the example response from the "Explanation" section of the previous question to complete the review prompt. 

<br>

Depending on how our observations differ and exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat link: `<url to your conversation>`

<br>

My feedback from ChatGPT suggested I could strengthen my list by asking about whether matrices must always be rectangular or could be jagged which would help cover edge cases, define the boundaries of the problem space, and clarify assumptions. I asked some follow up questions to better understand what a jagged array is. Since it wouldn't be a valid matrix, it sounds like I can ignore that possibility for this case.

<br>

ChatGPT also recommended asking about what types of data are allowed in the matrix, and whether error messages should be standardized. These don't seem relevant to the problem space since the type of data held by the original matrix does not affect reshaping, and the problem statement says "You may choose the specific error message".

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

Without writing code, describe how you would implement `reshape_matrix` in enough detail that another developer could reasonably implement a solution. We should capture the main use cases, but the steps do not need to be a detailed plan for every contingency. 
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

We want to know if we are laying out an approach to the coding problem that makes sense for our context and if that approach is clearly conveying our thoughts on technical topics to others. Let’s once more use an AI tool like ChatGPT, this time to review the Logical Steps we wrote above. Our goals are to check if:
- the steps make sense for the problem being solved
- the steps are not missing important steps or scenarios
- the steps are agnostic of any particular language – steps should not include code syntax.
- the steps are written with enough detail for another developer to understand how to create a solution

<br>

For this question we will:
1. Build a prompt using [the template linked here](https://gist.githubusercontent.com/ada-instructors/670252696f1625cf0ed77c0997cd165d/raw/pse_logical_steps_review_template.md)
2. Share the completed prompt with an AI tool like ChatGPT
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

As an example, let’s say we used logical steps similar to the explanation for the question above in our prompt. Depending on how the supplied steps differ and exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat Link: `<url to your conversation>`

<br>

ChatGPT's feedback said that the iteration details are clear, especially when to start a new row, and the description mostly avoids Python-specific constructs. There were a couple areas for improvement:
- I could clarify the output structure in a more language-agnostic way using “matrix” or “2D structure” instead of “2D list”, since lists are pretty specific to Python. 
- I should explicitly state what I mean by iterating in order, such as "iteration is row-major (left to right, top to bottom)" to avoid confusion. 

<br>

ChatGPT said edge cases like single-row or single-column inputs would make the approach more robust, but it also stated that "your steps do cover it". This is something I will keep in mind that I could clarify, and would want to write tests around, but it doesn't seem useful to break out specific edge cases in the algorithm's steps when those cases will be handled by the main flow of the function.

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->