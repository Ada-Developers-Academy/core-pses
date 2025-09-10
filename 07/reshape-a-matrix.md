# Reshape the Matrix

## Problem

In MATLAB, a programming platform for numeric computing, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size while keeping its original data.

You're given a matrix represented by a two-dimensional array, and two positive integers **r** and **c** representing the number of rows and number of columns of the intended reshaped matrix, respectively.

The reshaped matrix needs to be filled with all the elements of the original matrix in the same row-traversing order as they were.
- If the 'reshape' operation with given parameters is possible, output the new reshaped matrix.
- Otherwise, raise a `ValueError` (You may choose the specific error message)

**Example 1:**

```
Input: 
nums = 
[[1,2],
 [3,4]]
r = 1, c = 4

Output: 
[[1,2,3,4]]
```

**Explanation:**

The row-traversing of nums is [1,2,3,4]. The new reshaped matrix is a 1 * 4 matrix, fill it row by row by using the previous list.


**Example 2:**

```
Input: 
nums = 
[[1,2],
 [3,4]]
r = 2, c = 4

Output: 
ValueError
```

**Explanation:**

There is no way to reshape a 2 * 2 matrix to a 2 * 4 matrix, so we raise a ValueError.

**Example 3:**

```
Input: 
nums = 
[[1,2],
 [3,4],
 [5,6],
 [7,8]]
r = 2, c = 4

Output: 
[[1,2,3,4],
 [5,6,7,8]]
```

**Explanation:**

The original matrix was 4 * 2. The new reshaped matrix is a 2 * 4 matrix, fill it row by row by using the previous list.

**Note:**

It can be assumed that all given `r` and `c` are positive numbers.

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

2. The problem statment says the matrix we receive as an argument will be represented as a 2 dimensional array. In the examples, the outputs are also displayed as 2 dimensional arrays.
    - This means that the new matrix we create should also be a 2 dimensional array.

3. When discussing the output, it says we should raise a ValueError if the original matrix cannot be reshaped as requested.
    - I will need to do some check in my function to see if the number of items in the original matrix is equal to the number of items in the requested matrix before trying the reshape operation.

4. The problem statment says the new matrix needs to be filled with the elements of the old matrix in the same row-traversing order.
    - This means that the order of the elements in the new matrix matters. I will need to go row by row starting at the front of each list in the original matrix as I fill up the new matrix.

5. We can assume that the arguments to the function will be valid, so the input matrix will be a 2 dimensional list, and the `r` and `c` will not be negative, but are there any special considerations if the input matrix is empty?
    - There is nothing in the problem statment or examples that says this case should be treated any differently.
        - If I'm given an `r` or `c` greater than 0, then I cannot reshape the matrix and would raise a ValueError.
        - If the `r` and `c` are 0, there are technically the same number of elements in the original as `r * c`, so I would return a new, empty 2 dimensional list.

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

For an example of what a review response might look like, let’s say that we used the example response from the "Explanation" section of the previous question to complete the review prompt. 

<br>

Depending on exactly what ChatGPT shares, a reflection and summary might look like:

<br>

Chat link: `<url to your conversation>`

<br>

My feedback from ChatGPT suggested I could strengthen my list by asking about whether matrices must always be rectangular or could be jagged and clarifying how an “empty matrix” is defined. These additions would help cover edge cases, define the boundaries of the problem space, and clarify assumptions.

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
# example input 1: [[1,2], [3,4], [5,6], [7,8]]
#                  r = 2, c = 4
# expected output 1: [[1, 2, 3, 4]], [5, 6, 7, 8]]

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
def test_two_nominal_lists():
    # nominal test case
    # Arrange
    matrix = [[1], [2], [3], [4]]
    r = 1
    c = 4

    # Act
    result = reshape_matrix(matrix, r, c)

    # Assert
    assert result == [[1, 2, 3, 4]]

def test_empty_lists():
    # edge test case
    # Arrange
    matrix = []
    r = 0
    c = 0

    # Act
    result = reshape_matrix(matrix, r, c)

    # Assert
    assert result == []

def test_list_one_all_before_list_two():
    # alternative edge test case
    # Arrange
    matrix = [[1,2], [3,4]]
    r = 3
    c = 2

    # Act
    result = reshape_matrix(matrix, r, c)

    # Assert
    assert result == [[1,2], [3,4]]

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->


<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 1ece1eb2-0d72-4068-9ca6-f77ca49d73c5
* title: Create Logical Steps
* topics: pse

##### !question

Without writing code, describe how you would implement `reshape_matrix` in enough detail that someone else could write the code. 
* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

List logical steps to solve the problem

##### !end-placeholder

### !explanation

Example Steps:
1. Store the number of rows and number of columns in the matrix in variables `row` and `column`
2. If `row`*`column` does not equal `r`*`c`, return the `matrix`
3. Initialize an empty list `reshaped_matrix`
4. Iterate through the number of rows
5. Initialize a new row 
6. Iterate through the columns
7. Append the correct item to the new row
8. Append the new row to the `reshaped_matrix`
9. return the `reshaped_matrix`

### !end-explanation

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

