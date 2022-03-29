# Reshape the Matrix

## Problem

In MATLAB, there is a very useful function called 'reshape', which can reshape a matrix into a new one with different size but keep its original data.

You're given a matrix represented by a two-dimensional array, and two positive integers **r** and **c** representing the number of rows and number of columns of the wanted reshaped matrix, respectively.

The reshaped matrix need to be filled with all the elements of the original matrix in the same row-traversing order as they were.

If the 'reshape' operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.

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
[[1,2],
 [3,4]]
```

**Explanation:**

There is no way to reshape a 2 * 2 matrix to a 2 * 4 matrix. So output the original matrix.

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

The height and width of the given matrix is in range [1, 100].
The given r and c are all positive.

Sourced from:  [Leetcode](https://leetcode.com/problems/reshape-the-matrix/)

## Prompts:

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->
<!-- Replace everything in square brackets [] and remove brackets  -->

### !challenge

* type: paragraph
* id: 931b7218-6fc5-4fd5-9b6c-7945856a6041
* title: Ask Clarifying Questions
* topics: pse

##### !question

List three or more questions whose answers would clarify the problem statement

##### !end-question

##### !placeholder

Give three clarifying questions.

##### !end-placeholder

<!-- other optional sections -->
<!-- !hint - !end-hint (markdown, users can see after a failed attempt) -->
<!-- !rubric - !end-rubric (markdown, instructors can see while scoring a checkpoint) -->
##### !explanation

Here are some example clarifying questions:

1.  Are there any constraints on matrix sizes?
1.  Can a matrix have 1 row or 1 column?
1.  What if the matrix is empty or `None`?

##### !end-explanation

##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint

##### !rubric

- The answer is wrong if there aren't at least three questions

##### !end-rubric

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- Question 2 -->
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

def test_list_1_all_before_list_2():
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
* points: 3
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

